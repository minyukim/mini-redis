# Mini Redis

My own learning journey of writing a mini Redis client and server in Rust with Tokio (https://tokio.rs/tokio/tutorial).

## Difference from the tutorial

- Implement a generic shared map struct used as a shared database for the server. It prevents:
  - Leaking the implementation details. For example, the outside world doesn't need to be changed when you change the Mutex to an RwLock.
  - Holding the mutex locked for too long by accident. This is particularly bad in async code, because `.await` can happen while a mutex is locked, which can cause deadlocks.

## Try it out

### Prerequisites

- [rustup](https://rustup.rs/)

### Server

### Client
