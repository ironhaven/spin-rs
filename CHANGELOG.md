# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

# Unreleased

### Added

- Default type parameter on `Once` for better ergonomics

### Changed

### Fixed

# [0.9.0] - 2021-03-18

### Changed

- Placed all major API features behind feature flags

### Fixed

- A compilation bug with the `lock_api` feature

# [0.8.0] - 2021-03-15

### Added

- `Once::get_unchecked`
- `RelaxStrategy` trait with type parameter on all locks to support switching between relax strategies

### Changed

- `lock_api1` feature is now named `lock_api`

# [0.7.1] - 2021-01-12

### Fixed

- Prevented `Once` leaking the inner value upon drop

# [0.7.0] - 2020-10-18

### Added

- `Once::initialized`
- `Once::get_mut`
- `Once::try_into_inner`
- `Once::poll`
- `RwLock`, `Mutex` and `Once` now implement `From<T>`
- `Lazy` type for lazy initialization
- `TicketMutex`, an alternative mutex implementation
- `std` feature flag to enable thread yielding instead of spinning
- `Mutex::is_locked`/`SpinMutex::is_locked`/`TicketMutex::is_locked`
- `Barrier`

### Changed

- `Once::wait` now spins even if initialization has not yet started
- `Guard::leak` is now an associated function instead of a method
- Improved the performance of `SpinMutex` by relaxing unnecessarily conservative
  ordering requirements

# [0.6.0] - 2020-10-08

### Added

- More dynamic `Send`/`Sync` bounds for lock guards
- `lock_api` compatibility
- `Guard::leak` methods
- `RwLock::reader_count` and `RwLock::writer_count`
- `Display` implementation for guard types

### Changed

- Made `Debug` impls of lock guards just show the inner type like `std`
