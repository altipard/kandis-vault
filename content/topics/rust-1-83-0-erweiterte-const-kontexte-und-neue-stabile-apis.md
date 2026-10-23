+++
title = "Rust 1.83.0: Erweiterte const-Kontexte und neue stabile APIs"
slug = "rust-1-83-0-erweiterte-const-kontexte-und-neue-stabile-apis"
date = 2026-10-23
updated = 2026-10-23

[taxonomies]
tags = [
    "rust",
    "rust-1.83",
    "const",
    "compilezeit",
    "static",
    "release",
    "unsafecell",
]

[extra]
summary = "Überblick über die Neuerungen in Rust 1.83.0, vor allem die erweiterten Möglichkeiten in const-Kontexten, also bei Code, der zur Compilezeit ausgewertet wird."
sources = [
    "2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta",
]
+++

Das Rust-Team hat Version 1.83.0 angekündigt. Im Mittelpunkt stehen Erweiterungen für Code in const-Kontexten, den der Compiler zur Compilezeit auswertet. Dazu kommen mehrere APIs, die nun in const-Kontexten stabil sind.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>

## Verweise auf statische Variablen

- Konstanten (`const`) dürfen jetzt auf statische Variablen (`static`) verweisen.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>
- Das Lesen mutabler oder interior-mutabler statics bleibt in const-Kontexten verboten.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>
- Der Endwert einer Konstante darf keine Referenz auf mutable oder interior-mutable statics enthalten.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>
- Eine Konstante darf dagegen als Wert einen Raw-Pointer auf eine mutable static liefern.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>

## Mutabilität innerhalb von const-Berechnungen

- Mutable Referenzen sind in const-Kontexten erlaubt, solange sie nicht Teil des finalen Werts der Konstante werden.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>
- Mutable Raw-Pointer und `UnsafeCell` (Interior Mutability) werden in const-Berechnungen unterstützt.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>

## Neue in const-Kontexten stabile APIs

Mehrere zusätzliche Funktionen sind nun in const-Kontexten stabil. Die konkrete Liste fehlt in der vorliegenden Quelle und muss in den vollständigen Release Notes nachgelesen werden.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>

## Update und weitere Hinweise

Die Installation erfolgt über `rustup update stable`. Hinweise zu Cargo und Clippy verweisen auf die vollständigen Release Notes. Details dazu stehen in der Quelle nicht.<sup class="q"><a href="#2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta">1</a></sup>
