# Rate Limiting Algorithms

## 1. Token Bucket

In this algorithm, assume you’ve bucket full of tokens. When a request comes, a token has to be taken from the bucket so
it can be processed further. If there is no token available in the bucket, the request will be rejected. The token
bucket is also refilled based on per time unit.

Here we can limit the requests per user per time unit by assigning a bucket with fixed amount of tokens to each user.
When a user uses up all tokens in a given time period, we know that he has exceeded the limit and discard his requests
until his bucket is refilled.

## 2. Leaky Bucket

This algorithm is closely related to Token Bucket, where it provides a simple approach to rate limiting via a queue
which you can think of as a bucket holding the requests. When a request is registered, it is appended to the end of the
queue. At a regular interval, the first item on the queue is processed. If the queue is full, then additional requests
are discarded (or leaked).

The advantage of this algorithm is that it smooths out bursts of requests and processes them at an approximately average
rate. It’s also easy to implement on a single server or load balancer, and is memory efficient for each user given the
limited queue size.

## 3. Fixed Window

In this algorithm, a window size of N seconds (such as 60 or 600 seconds) is used to track the rate. Each incoming
request increments the counter for the window. If the counter exceeds a threshold, the request is discarded. The windows
are typically defined by the floor of the current timestamp, so 10:00:06 with a 60 second window length, would be in the
10:00:00 window.

The advantage of this algorithm is that it ensures more recent requests gets processed without being starved by old
requests. However, a single burst of traffic that occurs near the boundary of a window can result in twice the rate of
requests being processed, because it will allow requests for both the current and next windows within a short time.
Additionally, if many consumers wait for a reset window at the peak hour, then they may rush to your API at the same
time.

## 4. Sliding Log

Sliding Log rate limiting involves tracking a time stamped log for each consumer request. These logs are usually stored
in a hash set or table that is sorted by time. Logs with timestamps beyond a threshold are discarded. When a new request
comes in, we calculate the sum of logs to determine the request rate. If the request would exceed the threshold rate,
then it is held.

The advantage of this algorithm is that it does not suffer from the boundary conditions of fixed windows. The rate limit
will be enforced precisely and because the sliding log is tracked for each consumer, you don’t have the rush effect that
challenges fixed windows. However, it can be very expensive to store an unlimited number of logs for every request. It’s
also expensive to compute because each request requires calculating a summation over the consumers prior requests,
potentially across a cluster of servers. As a result, it does not scale well to handle large bursts of traffic or denial
of service attacks.

## 5. Sliding Window

A hybrid approach that combines the low processing cost of the fixed window algorithm, and the improved boundary
conditions of the sliding log algorithm. Like the fixed window algorithm, we track a counter for each fixed window.
Next, we account for a weighted value of the previous window’s request rate based on the current timestamp to smooth out
bursts of traffic.

For example, if the current window is 25% through, then we weight the previous window’s count by 75%. The relatively
small number of data points needed to track per key allows us to scale and distribute across large clusters.

