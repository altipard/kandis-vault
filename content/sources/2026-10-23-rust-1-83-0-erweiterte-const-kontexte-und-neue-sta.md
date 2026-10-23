+++
title = "Rust 1.83.0: Erweiterte const-Kontexte und neue stabile APIs"
slug = "2026-10-23-rust-1-83-0-erweiterte-const-kontexte-und-neue-sta"
date = 2026-10-23 22:53:48.929210+02:00

[taxonomies]
tags = [
    "rust",
    "release",
    "const-kontext",
    "compiler",
    "static",
]

[extra]
url = "https://blog.rust-lang.org/2024/11/28/Rust-1.83.0/"
kind = "article"
site = "blog.rust-lang.org"
topic = "rust-1-83-0-erweiterte-const-kontexte-und-neue-stabile-apis"
summary = "Der Rust-Team kündigt Version 1.83.0 an und stellt mehrere Erweiterungen für Code in const-Kontexten vor, also Code, den der Compiler zur Compilezeit auswertet. Const-Ausdrücke dürfen nun auf statische Variablen verweisen und mutable Referenzen sowie mutable Raw-Pointer und Interior Mutability innerhalb einer Konstantenberechnung nutzen. Der Endwert einer Konstante darf jedoch keine mutable oder interior-mutable statics referenzieren, und mutable Referenzen dürfen nicht Teil des Endwerts sein. Außerdem sind mehrere APIs nun in const-Kontexten stabil; die konkrete Liste dieser APIs fehlt im vorliegenden Text."
+++

Der Rust-Team kündigt Version 1.83.0 an und stellt mehrere Erweiterungen für Code in const-Kontexten vor, also Code, den der Compiler zur Compilezeit auswertet. Const-Ausdrücke dürfen nun auf statische Variablen verweisen und mutable Referenzen sowie mutable Raw-Pointer und Interior Mutability innerhalb einer Konstantenberechnung nutzen. Der Endwert einer Konstante darf jedoch keine mutable oder interior-mutable statics referenzieren, und mutable Referenzen dürfen nicht Teil des Endwerts sein. Außerdem sind mehrere APIs nun in const-Kontexten stabil; die konkrete Liste dieser APIs fehlt im vorliegenden Text.

## Kernaussagen

- Konstanten (const) dürfen jetzt auf statische Variablen (static) verweisen, außer das Lesen mutable oder interior-mutable statics bleibt in const-Kontexten verboten.
- Der Endwert einer Konstante darf keine Referenz auf mutable oder interior-mutable statics enthalten.
- Eine Konstante darf als Wert einen Raw-Pointer auf eine mutable static liefern.
- Mutable Referenzen sind in const-Kontexten erlaubt, solange sie nicht Teil des finalen Werts der Konstante werden.
- Mutable Raw-Pointer und UnsafeCell (Interior Mutability) werden in const-Berechnungen unterstützt.
- Mehrere zusätzliche Funktionen sind nun in const-Kontexten stabil; deren Liste ist im Text nicht enthalten.
- Die Installation erfolgt über rustup update stable; Hinweise zu Cargo und Clippy verweisen auf die vollständigen Release Notes.

---

Autor: Nov  
Veröffentlicht: 2024-11-28
