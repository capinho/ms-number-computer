# ms-number-computer

A microservice that performs arithmetic operations.

## Description

This microservice is responsible for computing arithmetic operations such as addition, subtraction, multiplication, and division. It is designed to be scalable and fault-tolerant using the Hydra framework.

## Requirements

- Node.js (v14 or higher)
- Redis

## Installation

1. Clone the repository:

```
git clone https://github.com/capinho/ms-main-node.git
```

2. Navigate to the `ms-number-computer` directory:

```
cd ms-number-computer
```

3. Install the dependencies:

```
npm install
```

4. Start the microservice:

```
npm run development
```

## Usage

### Sending messages

To send a message to the `ms-number-computer` microservice, use the following endpoint:

```
POST http://localhost:9000/ms-number-computer/message
```

The message should have the following format:

```
{
  "topic": "<operation>",
  "payload": {
    "a": <number>,
    "b": <number>
  }
}
```

- `<operation>` can be one of the following: `add`, `subtract`, `multiply`, or `divide`.
- `<number>` is a number.

### Receiving messages

The `ms-number-computer` microservice subscribes to the following topics:

- `add`: computes the sum of two numbers.
- `subtract`: computes the difference between two numbers.
- `multiply`: computes the product of two numbers.
- `divide`: computes the quotient of two numbers.

To subscribe to a topic, use the following endpoint:

```
POST http://localhost:9000/ms-number-computer/subscribe
```

The request body should have the following format:

```
{
  "topic": "<operation>"
}
```

- `<operation>` can be one of the following: `add`, `subtract`, `multiply`, or `divide`.

### Testing

To run the test suite, use the following command:

```
npm test
```

## License

This microservice is licensed under the MIT License.%
