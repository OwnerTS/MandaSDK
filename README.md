# MandaSDK
SDK плагинов MandaGram-a

## Состав

- `include/` — C/C++/Zig-заголовки нативного API (`mandagram_plugin.*`, `jni_accessor.*`).
- `bindings/d/` — D-биндинги (`mandagram_plugin.d`, `dub.json`).
- `examples/{cpp,rust,zig}/` — минимальные примеры плагинов.

## Сборка примеров

- Zig (нужен Zig 0.15.x): `cd examples/zig && zig build -Doptimize=ReleaseFast`
- C++: `g++ -shared -fPIC -O2 -I include examples/cpp/plugin.cpp -o sample_plugin.so`
- Rust: `cargo build --release --manifest-path examples/rust/Cargo.toml`
- D (нужны ldc/dmd + dub): `cd bindings/d && dub build --build=release`

Собранная библиотека кладётся в каталог `plugins/` рядом с клиентом.
CI (`build-sdk`) собирает все примеры на каждый push/PR в `main`.
