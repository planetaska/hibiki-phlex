# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- `LICENSE-MIT.txt` and `LICENSE-APACHE.txt`, shipped in the gem. The repo
  carried no license text before, although the gemspec declared MIT.
- This changelog, linked from the gem page on rubygems.org.

### Changed

- **Dual-licensed under MIT or Apache 2.0**, at the user's option.

## [0.1.0] - 2026-07-18

First release, extracted from the hibiki monorepo.

### Added

- `Hibiki::Phlex::Rerenderable`, so the same component instance can render
  again without losing its signals.
- `Hibiki::Phlex.render_effect(component, scheduler: nil) { |html| ... }`: an
  effect that re-renders the component whenever a signal it read changes, and
  yields the fresh HTML to the block. The first run is the initial render, and
  its HTML is yielded too.
- Depends on hibiki `~> 0.1` and phlex `>= 2.4, < 2.5`. The upper bound is
  strict because `Rerenderable` relies on a private Phlex ivar;
  `spec/phlex_contract_spec.rb` guards it.

[Unreleased]: https://github.com/planetaska/hibiki-phlex/compare/v0.1.0...HEAD
[0.1.0]: https://github.com/planetaska/hibiki-phlex/releases/tag/v0.1.0
