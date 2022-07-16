---
title: "Projects"
---
This is an informal list of some projects I've worked on. Most of these were done in my spare time.  

# tlsf-pmr

[tlsf-pmr](https://github.com/LiemDQ/tlsf-pmr) is a C++17 implementation of the Two-Level Segregated Fit (TLSF) memory allocator by Masmano et al. (2004), but adapted for use with the `std::pmr` polymorphic allocator API and with a permissive license (compared to the reference C implementation, which has a GPL license). 

This allows it to be used in any standard library container or algorithm that accepts custom memory allocators, such as `std::vector`. TLSF is a pool allocator features an allocation complexity of $O(1)$, as well as low levels of fragmentation, making it appropriate for use cases that require deterministic execution times, such as real-time applications. The original paper can be found [here](http://www.gii.upv.es/tlsf/files/ecrts04_tlsf.pdf).

In line with the recommendations of [this talk](https://www.youtube.com/watch?v=LIb3L4vKZ7U) on memory allocator design by Andrei Alexandrescu, it also features the ability to configure custom upstream allocators, which are used when the pool has insufficient memory to support an allocation. 

![TLSF data structures](/img/TLSF.png "An overview of the allocation algorithm. It makes sense if you read the paper. I swear.")

# hustl
[hustl](https://github.com/LiemDQ/hustl) is a performant, cross-platform STL file viewer written in Rust. It is written to support complex, high-polygon shapes and supports GPU acceleration using WebGPU and compiles to both native binaries and WebAssembly. It has very fast load times thanks to the use of vertex indexing along with extensive parallelism&mdash;it can load a 3 million polygon model (pictured below) in around 270ms on an AMD Ryzen 5 3600X CPU and a GeForce GTX 660. I suppose you could call it *blazingly fast* :rocket: :point_left: :sunglasses: :point_left: 

<figure>
<img src="/img/hustl_ss2.png" width="75%">
<figcaption>Model obtained from Szimuly Casba on <a href="https://grabcad.com/library/wonder-woman-2">GrabCad</a>.</figcaption>
</figure>

# rucksacc - WIP
[rucksacc](https://github.com/LiemDQ/rucksacc) is a C compiler that aims to be compliant with C11, written in Rust and using the Cranelift code generation backend. It is fairly fully-featured, supporting the preprocessor as well as code optimizations. However, it should still be considered a "toy" compiler. In particular, robust error handling is one of the trickiest parts of modern compiler frontends, and Rucksacc's implementation is fairly simplistic.

Rephrased in technical jargon, rucksacc is a multi-pass compiler frontend that uses a [control-flow graph](https://en.wikipedia.org/wiki/Control-flow_graph) intermediate representation, but defers optimization details like register allocation to Cranelift. The parsing step uses a hand-coded recursive descent parser, but uses [Pratt parsing](http://journal.stuffwithstuff.com/2011/03/19/pratt-parsers-expression-parsing-made-easy/) to evaluate expressions. The [C lexing problem](https://en.wikipedia.org/wiki/Lexer_hack) is solved by deferring identifier classification to the semantic analysis step.

<!-- 
# Shine - WIP
[Shine](https://github.com/LiemDQ/shine) is a basic raytracer, written in Rust. It is capable of simulating diffraction, reflection, refraction, focal blur, shadows, and more!

Shine was written from scratch, with only a single 3rd-party dependency (for random number generation). -->

# Sounding rockets
As an undergraduate student, one of my main extracurricular activities was building and flying high-powered [sounding rockets](https://en.wikipedia.org/wiki/Sounding_rocket).

[Caladan](/doc/MRT_Caladan_Technical_Report.pdf) was a 30,000 ft solid motor rocket built and flown at [Spaceport America Cup (SAC) 2019](https://spaceportamericacup.com/), completely built and designed from scratch by students. 

![A picture of Caladan](/img/rocket_surgery.jpg "Burning the midnight oil performing rocket surgery on Caladan")

[Blanche](/doc/MRT_Blanche.pdf) was a 10,000 ft solid motor rocket flown at SAC 2018, where it placed 1st in its category and went on to win the Spaceport America Cup. 

![A group picture of Blanche](/img/blanche_group_photo.jpg "Smelly, sleepless students smile sunnily with Blanche in foreground")

[Ariel](/doc/Ariel_PDR.pdf) was a proposed 300,000 ft apogee liquid engine rocket that would have been, at the time, the first student-researched-and-designed liquid rocket to breach the Karman line. Due to manpower and schedule restrictions, Ariel was shelved after the preliminary design stage, thereby joining a long, illustrious list of aerospace vehicle concepts that get cancelled before ever seeing the light of day. 

# Characterization of metal oxide water splitting catalysts
In undergrad, I worked in a [research lab](http://electrochem.mcgill.ca/electrochem.mcgill.ca/index.html) where we produced and characterized cathodes for the hydrogen evolution reaction, a.k.a. water splitting for green hydrogen production. Our motivation was to determine to what extent adding iridium to nickel-molybdenum oxides would improve their electrocatalytic performance. Iridium is a very good water splitting catalyst, but is very expensive; molydenum and nickel are much cheaper but are less effective. 

![Tafel polarization curves](/img/tafel.png "Tafel polarization curves for some of the samples we tested.")

Additionally, nickel electrodes are prone to degradation in acidic media (found in, e.g., [PEM fuel cells](https://en.wikipedia.org/wiki/Proton-exchange_membrane_fuel_cell)); using *oxides* makes them more resistant to degradation, but with the tradeoff of reduced performance. 

The result of our work was published in *Electrochimica Acta*. A copy of the paper can be found [here](/doc/vidales2019.pdf).