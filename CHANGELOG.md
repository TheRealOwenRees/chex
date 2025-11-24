# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## 0.2.0-alpha.2

### Changed

Fixed deprecated code that was picked up by Dialyzer

## 0.2.0-alpha.1

A brief update to allow the library to compile with modern versions of Elixir. This allows the user to take advantage of the latest added functions by [Andrew Lechowicz](https://github.com/alecho/chex), which includes `possible_moves/2`.

### Changed

- Updated below dependencies to latest versions:
  - mix_test_watch
  - `credo`
  - `dialyxir`
- Updated `config.exs` to use the modern `import Config` at the top of the file
- Project compiles with `elixir 1.18.4-otp-28`

## [Unreleased 0.2.0] - Last work from [Andrew Lechowicz](https://github.com/alecho/chex) from which this fork is based.

### Added

- This CHANGELOG.
- Public API! `Chex`.
- LICENSE file with MIT license.
- Castling support.
- Checkmate support.
- Stalemate support.
- `:pgn` key for games that were imported from a PGN file. This is `nil` or a
  map with keys from the tag pair section. Known supported keys such as the STR
  are converted to atoms others remain strings.

### Changed

- `Parser.FEN.parse/1` and `Parser.FEN.serialize/1` now return a tuple with
  `{:ok, result}` or `{:error, reason}`.

### Removed

- `:fen` from `%Chex.Game{}`. You can now serialize a game with modules that
  implement the Chex.Parser behaviour like `Chex.Parser.FEN.serialize(game)`.
- OTP application functionality. Users should implement their own state
  management as they see fit for their use case.
- `Game.to_fen` in favor of calling the serializer function directly.
