## Wafer Production System : Modelling and Verification

Present here are files created as part of the System Validation project for Q1 2018-19 by @evil-scientist and team.
The aim of the project is to design, verify and test a controller for Industrial transfer system for silicon wafers

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for testing and verification purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

You need to install mcrl2 to replicate our results.

After installing, either use our Makefile or run the following command.
```
mcrl2-gui
```

## Running the tests

To run the automated tests for this system, use the Makefile provided.

The following creates all of the required files
```
make all
```

Then you can execute: 

```
make sim
make view
```
for simulation and visualization of the system.

The following will test all of the μ calculus formaluae
```
make tests
```
Once finished, run
```
make clean
```
This will remove all intermediate files

## Deployment

The project has been tested on 
* Windows 10, Intel i-core i7, 2.8GHz processor with 16GB RAM 
* Xubuntu (18.04), Intel i-core i5, 2.8GHz processor with 8GB RAM

Clone the repository on to your machine, install mcrl2 and run the Makefile as instructed.

## Built With

* [mcrl2](https://www.mcrl2.org/web/user_manual/index.html) - The tools and framework used [201808.0]
* [draw.io](https://draw.io/) - Used to make the Architecture
* [TexWorks](http://www.tug.org/texworks/) - Used for Report (LaTeX)

## Authors

* **Suryansh Sharma** - [TU Delft](https://github.com/evil-scientist)
* **Suhail Nogd** - [TU Delft](https://github.com/SuhailN)
* **Snehal Jauhri** - [TU Delft](https://github.com/sjauhri)
* **Apoorva Arora** - [TU Delft](https://github.com/apoorvaarora79)

The list of [contributors](https://github.com/evil-scientist/system-validation-project/contributors) who participated in this project.

## License

This project is licensed under the MIT License
