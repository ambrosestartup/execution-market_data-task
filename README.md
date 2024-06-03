# execution-market_data-task
A Java-based market data factory

## Summary
This task involves creating a Java-based market data factory, emphasizing concurrent processing and efficient data handling in a financial context. The system is structured around incoming events (external market data), the LMAX Disruptor and a subscription service for internal parts of the system to access such transformed market data events into market data structures.

Note that you only need to implement this service for orderbook style market data and for a single exchange of your choice e.g. Binance, but the event should be built in a way such that you could easily pass another type of market data and venue. [You can create a dummy / simulator class to mimic order book [market data events] and send those to the disruptor.]
### Core Components
1. Market data events: This component is responsible for efficiently producing market data events to the LMAX Disruptor. The event should include information about the market data type e.g. orderbooks, the venue, the trading contract...
2. LMAX Disruptor setup: Check the documentation and setup an LMAX disruptor / ring buffer with appropriate event handlers to process market data events.
3. Market data structures: In this example, your event handler should process market data event and update the state of your orderbook that lives in the market data structure class / factory.
4. Market data subscription serivce: Allow for other parts of system to have access to market data state and any new events / changes to the market data. Observer pattern could work here / can be creative here.
5. Add other event handler templates [don't need too much detail] for journalling, saving in cache or redis?
### Requirements
1. Java and Concurrency: Implement the service using Java and its concurrency utilities.
2. LMAX Disruptor: Implement this for processing events.
3. Redis?: Utilize Redis for saving state of orderbook, so have access in memory DB + local cache [optional]
4. Documentation & Testing: Provide a README file detailing how to run the service and its tests, along with a brief explanation of design choices.
### Additional Notes
- Design Flexibility: Candidates are free to choose appropriate patterns for low latency services.
- Environment Setup: Use of Docker for environment setup is encouraged but not mandatory.
#### Evaluation Criteria
Candidates will be evaluated based on:
1. Correctness
2. Effective use of Java's concurrency utilities
3. Low latency design
4. Code quality
5. Clear and informative documentation
6. Comprehensive testing
7. Efficient Redis usage

#### Expected Time Commitment
The task is expected to take approximately 3-4 hours. This estimate includes developing the core services, writing tests, and documentation. Candidates should aim for a balance between innovative solutions and practical implementation within this time frame.
This test aims to assess the candidate's technical skills and their ability to deliver a functional, well-designed system in a realistic timeframe, mirroring real-world project constraints.
