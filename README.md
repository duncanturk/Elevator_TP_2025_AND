# Elevator Term Project

## Overview

This repository contains the term project for the **Correctness by Construction** lecture at Universidad Politécnica de Madrid (UPM), taught by Prof. Manuel Carro. The project demonstrates the application of formal methods to model and verify the correctness of an elevator control system using Event-B.

## Course Information

- **Course**: Correctness by Construction
- **Institution**: Universidad Politécnica de Madrid (UPM)
- **Professor**: Prof. Manuel Carro
- **Course Website**: https://wp.software.imdea.org/cbc/

## Team Members

- Christopher Roßbach
- David Hospodka  
- Antonio José Fernández Pinto

## Project Description

This project models an elevator control system using Event-B formal methods to ensure correctness by construction. The system addresses key functional requirements including:

- **Elevator Movement Control**: Ensuring the elevator moves only when there are pending requests and in appropriate directions
- **Door Management**: Modeling door opening/closing behavior with safety constraints
- **Request Handling**: Managing floor requests and ensuring all requests are eventually served
- **Safety Invariants**: Maintaining critical safety properties throughout system operation

## Technical Approach

### Formal Modeling with Event-B

The project uses Event-B, a formal method for system-level modeling and analysis. Key aspects include:

- **Stepwise Refinement**: The system is developed through multiple refinement levels
  - Machine 0 (Base Model): Basic elevator behavior
  - Machine 1: Enhanced with detailed algorithms and transitions
- **Invariant-Based Verification**: Critical safety properties are expressed as invariants and formally verified
- **Event-Driven Architecture**: System behavior is modeled through events with guards and actions

### Tools Used

- **Rodin Platform**: Primary development environment for Event-B modeling
- **ProB Model Checker**: Used for model validation and invariant violation detection
- **LaTeX/Beamer**: For presentation and documentation

### Key Requirements Addressed

The system implements formal specifications for various functional requirements:

- **FUN 15**: The elevator should not move if there are no requests waiting to be served
- **FUN 16**: The elevator should not move in a direction where there are no pending requests to attend
- **FUN 6**: The elevator can receive signals to move to any level and stops automatically when reached
- **FUN 7**: The elevator has doors that can be controlled (opened/closed)

## Repository Structure

```
├── deliverables/                    # Final project deliverables
│   ├── Elevator_TP_2025_AND_explanations.pdf
│   ├── Elevator_TP_2025_AND_slides.pdf
│   └── Elevator_TP_2025_AND.zip
├── presentation/                    # LaTeX presentation source
│   ├── presentation.tex
│   ├── basix.sty
│   └── img/
├── latex/                          # LaTeX style files
│   └── bsymb.sty
├── elevator-c0*                    # Event-B context files
├── elevator-m0*                    # Event-B machine files (base model)
├── elevator-m1*                    # Event-B machine files (refined model)
└── *.bpo, *.bpr, *.bps            # Rodin proof files
```

## Event-B Files

- **Contexts (.bcc, .buc)**: Define the mathematical foundation, sets, constants, and axioms
- **Machines (.bcm, .bum)**: Define the dynamic behavior through variables, invariants, and events
- **Proof Files (.bpo, .bpr, .bps)**: Contains proof obligations and their discharge status

## Key Features Modeled

1. **Elevator Algorithm**: Implementation of a standard elevator scheduling algorithm
2. **State Transitions**: Formal modeling of elevator state changes
3. **Liveness Properties**: Ensuring the system eventually serves all requests
4. **Deadlock Freedom**: Verification that the system cannot reach deadlock states
5. **Environment Interaction**: Modeling of sensor inputs and actuator outputs

## Verification Results

The project demonstrates successful formal verification including:

- Automatic discharge of proof obligations for most invariants
- Model checking with ProB for different floor configurations (1-5 floors)
- No invariant violations found during exhaustive state space exploration
- Manual proof intervention required for complex invariants involving mathematical functions

## How to Work with This Project

### Prerequisites

- Rodin Platform (Eclipse-based Event-B development environment)
- ProB model checker plugin
- LaTeX distribution (for building presentation)

### Opening the Project

1. Import the project into Rodin workspace
2. The main models are:
   - `elevator-m0.bum`: Base machine model
   - `elevator-m1.bum`: Refined machine model  
   - `elevator-c0.buc`: Context definitions

### Building Presentation

```bash
cd presentation/
pdflatex presentation.tex
pdflatex presentation.tex  # Run twice for references
```

## Academic Context

This project exemplifies the **Correctness by Construction** methodology, which emphasizes:

- Building systems that are correct from the outset rather than debugging after implementation
- Using mathematical foundations to specify system behavior
- Applying formal verification techniques to ensure properties hold
- Stepwise refinement to manage complexity while preserving correctness

## Related Resources

- Course Website: https://wp.software.imdea.org/cbc/
- Event-B Official Site: http://www.event-b.org/
- Rodin Platform: http://wiki.event-b.org/index.php/Rodin_Platform

---

*This project demonstrates the practical application of formal methods in developing safety-critical systems, showcasing how mathematical rigor can be applied to ensure system correctness from specification through implementation.*