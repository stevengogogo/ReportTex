# ReportTeX: A LaTeX template supporting both English and Traditional Chinese

[![.github/workflows/ci.yml](https://github.com/stevengogogo/ReportTex/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/stevengogogo/ReportTex/actions/workflows/ci.yml)


**ReportTeX** is a LaTeX pipeline for generating reports and manuscripts. This template uses [tectonic](https://github.com/tectonic-typesetting/tectonic) engine to avoid cumbersome installation of MacTex (just try `brew install tectonic` :) ), and this is an big life-saver ! 

This pipeline also supports Chinese characters, which are difficult to render with the TeX engine. Fourtunely, `tectonic` is based on XeTeX which supports `UTF8` characters. The sample below is the output of a mixture of English and Manderin words:

|<img width="859" alt="Screen Shot 2021-03-12 at 6 50 57 PM" src="https://user-images.githubusercontent.com/29009898/110930292-e3190200-8363-11eb-9f15-2c4f47b68371.png">|<img width="860" alt="Screen Shot 2021-03-12 at 6 51 45 PM" src="https://user-images.githubusercontent.com/29009898/110930386-017efd80-8364-11eb-902d-e82908c36310.png">|
|---|---|

Besides, this CI provides early bug detection and helps you to fix `tex` file during composition. To my knowlege, this is the easist pipeline to work on Latex with Manderin article. Enjoy😄.

## How to build `main.tex`?

In the terminal simply type 

```bash
make
```

or

```bash
make build
```

or if you don't have `make`

```bash
tectonic main.tex
```

## How is this repo organized?


|FileName|Description|
|---|---|
|`main.tex`|Write your article here|
|`setup.tex`|Layout setting. You can customize your setting here, or put template permeable|
|`library.bib`|Reference collection|
|`fig/`|Image folder|
|`makefile`|Script for generating PDF output. Type `make` in terminal|
|`.github`|Continuous Integration with [tectonic](https://github.com/tectonic-typesetting/tectonic), a modern LaTeX compiler written in Rust|
|`fonts.txt`|URLs of additional fonts. If you want more, please visit the noto font website and append the url(s) to it.|

*Notice that Manderin fonts is usually cumbersome to setup. This process is largely redueced by*  @sosiristseng

## How to work on the TeX file(s) locally

### Linux

1. [Install tectonic](https://tectonic-typesetting.github.io/en-US/install.html)
2. Install addtional fonts if needed, for example,  `sudo apt install` in Ubuntu-based systems.
3. `tectonic main.tex` and profit!

Also see the [Gihub CI config file](.github/workflows/ci.yml)

### MacOS

- Install fonts
     - Download [Noto Font](https://www.google.com/get/noto/#sans-hant)：
     - Put `.otf` into FontBook (A build-in software in MacOS for organizing fonts)
     ![Screen Shot 2021-03-12 at 1.41.23 PM](https://i.imgur.com/WqanmTB.jpg)
- Install `tectonic`
  ```bash
  brew install tectonic
  ```

- 🎉 Complete installation: 
     The PDF can be built by typing 
     ```
     make
     ```
     in terminal. The automation is supported by the [makefile](makefile). Change it if you need customization.

## Features

- Tectonic
     - Easy installing
     - Auto downloading `sty` files
     - Light and fast
- Self-hosted
     - No need to limit to Overleaf's IDE 
     - Allow to use Git branches for precise version control
- Github CI
     - Allow testing before merging to your final results
     - Detect errors / bugs early.
