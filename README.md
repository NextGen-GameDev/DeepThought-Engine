<div id="top"></div>

<div align="center">
  <a href="https://github.com/P1ayer-1/DeepThought-Engine">
    <img src="Resources/Icon128.png" alt="Logo" width="128" height="128">
  </a>
<h3 align="center">DeepThought Engine</h3>
  <p align="center">Driving Open Source Innovation in Game Development with Advanced AI Integration</p>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url] 
</div>


<div align="center">

[![](https://dcbadge.limes.pink/api/server/AWWECeRcyX?theme=default-inverted)](https://discord.gg/AWWECeRcyX)
</div>

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;



**Table of Contents**
1. [About the Plugin](#about-the-plugin)
   - [Features](#features)
2. [Getting Started](#getting-started)
   - [Prerequisites](#prerequisites)
   - [Installation](#installation)
   - [Backend Setup](#backend-setup)
   - [Tokenizers Plugin Setup (Optional)](#tokenizers-plugin-setup-optional)
3. [Guides and Tutorials](#guides-and-tutorials)
   - [YouTube Tutorials](#youtube-tutorials)
   - [Wiki](#wiki)
4. [Contributing](#contributing)
5. [License](#license)

---

## About the Plugin

<div id="about-the-plugin"></div>

DeepThought Engine is an _experimental_ Unreal Engine plugin designed to facilitate the integration and use of various machine learning model architectures. Inspired by HuggingFace Transformers' relationship with PyTorch, DeepThought Engine goes beyond to support a diverse range of models.

### Features

<div id="features"></div>

- Integrate diverse machine learning model architectures within Unreal Engine.
- Easily interact with Transformer models.
- Utilize the power of [LibTorch](https://pytorch.org/cppdocs) for deep learning operations.
- Seamlessly tokenize and preprocess data using [Tokenizers-UE5](https://github.com/P1ayer-1/Tokenizers-UE5).
- Future-proof design with planned support for multiple backends.

<p align="right">(<a href="#top">back to top</a>)</p>

## Getting Started

<div id="getting-started"></div>

To get started with DeepThought Engine, ensure you have the necessary prerequisites and follow the installation instructions.

### Prerequisites
<div id="prerequisites"></div>

_In order for this plugin to work, additional files which are not present in this repository are required._
_Those files can be accessed from the official [PyTorch website](https://pytorch.org/get-started/locally/)._

- **OS**: Windows - 64 bit
- **UE Version**: 5.0 - 5.3
- **GPU Support**: CUDA-only (for GPU acceleration)
- **[LibTorch-UE5 Plugin](https://github.com/P1ayer-1/LibTorch-UE5)**: Required (only backend available for now)
- **[Tokenizers-UE5 Plugin](https://github.com/P1ayer-1/Tokenizers-UE5)**: Optional (for tokenization functionality)



### Installation

<div id="installation"></div>

1. In your Unreal Engine project, create a `Plugins` folder if it doesn't already exist.
2. Clone this repository inside the `Plugins` folder:
```shell
git clone https://github.com/P1ayer-1/DeepThought-Engine.git
```



### Backend Setup

<div id="backend-setup"></div>

DeepThought Engine currently supports [LibTorch](https://pytorch.org/cppdocs) as the primary backend. Follow these steps to set up LibTorch:

#### Method 1: LibTorch-UE5 Releases

1. Navigate to the [Releases page](https://github.com/P1ayer-1/LibTorch-UE5/releases).
2. Download the source code for a release of the LibTorch-UE5 plugin.
3. Extract the source code archive to the `Plugins` folder.
4. Download the CPU or GPU LibTorch distribution from the same release.

#### Method 2: LibTorch-UE5 Repo (For Developers/Contributors)

1. Clone the [LibTorch-UE5](https://github.com/P1ayer-1/LibTorch-UE5) repository inside the `Plugins` folder:
```shell
git clone https://github.com/P1ayer-1/LibTorch-UE5.git
```
2. Download the appropriate CPU or GPU LibTorch distribution from the [official PyTorch website](https://pytorch.org/get-started/locally/).
3. Extract the `include` and `lib` folders from the downloaded LibTorch archive into `Plugins/LibTorch-UE5/Source/ThirdParty/LibTorch/Win64`.

#### Common Steps for Both Methods

After you have downloaded the required files, follow the steps below:

1. Extract the `include` and `lib` folders to `Plugins/LibTorch-UE5/Source/ThirdParty/LibTorch/Win64`.
2. Navigate to `Plugins/LibTorch-UE5/Source/ThirdParty/LibTorch/Win64`.
3. Remove the `include` folder.
4. Extract the `include` and `lib` folders from the downloaded LibTorch release.
5. Go to `include/torch/csrc/api/include/torch/enum.h`.
6. Find the following line of code:
```c++
TORCH_API extern const enumtype::k##name k##name;
```
7. Remove `TORCH_API extern` from the aforementioned line of code.
8. Go to `include/torch/csrc/api/include/torch/nn/module.h`.
9. Find the following comment in the `Module` class:
```c++
// Friend classes.
```
10. Add the following line of code below the comment:
```c++
friend class IAtumLayer;
```



### Tokenizers Plugin Setup (Optional)

<div id="tokenizers-plugin-setup-optional"></div>

1. Navigate to the [Releases page](https://github.com/P1ayer-1/Tokenizers-UE5/releases).
2. Download the source code for the release you want to use.
3. Extract the downloaded source code into the `Plugins` directory.
4. Navigate to `Plugins/Tokenizers-UE5/Source/ThirdParty/TokenizersLibrary/Win64`.
5. From the same release page, download `tokenizers_c.lib` and place it inside the `Win64` folder.
6. Delete the placeholder file named `PLACE STATIC LIB HERE` from the `Win64` folder.

<p align="right">(<a href="#top">back to top</a>)</p>

## Guides and Tutorials

<div id="guides-and-tutorials"></div>

**Disclaimer:** The tutorials were published before this plugin was created. They only focus on `Tokenizers-UE5` and `LibTorch-UE5`.

### YouTube Tutorials

<div id="youtube-tutorials"></div>

- [Setup and Basic Usage](https://youtu.be/dvGWUh4SPBY)
- [Working with Meta's Llama](https://youtu.be/0YI2O5uSuFw)

### Wiki

<div id="wiki"></div>

- [https://github.com/gpt-3d/pytuech/wiki](https://github.com/gpt-3d/pytuech/wiki)

<p align="right">(<a href="#top">back to top</a>)</p>

## Contributing

<div id="contributing"></div>

Interested in contributing? Great! Check out the [contributing guidelines](CONTRIBUTING.md) to get started. Contributors are also encouraged to join our [community Discord server](https://discord.gg/AWWECeRcyX).

<p align="right">(<a href="#top">back to top</a>)</p>

## License

<div id="license"></div>

Distributed under the MIT License. See `LICENSE` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>


[contributors-shield]: https://img.shields.io/github/contributors/P1ayer-1/DeepThought-Engine.svg?style=for-the-badge
[contributors-url]: https://github.com/P1ayer-1/DeepThought-Engine/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/P1ayer-1/DeepThought-Engine.svg?style=for-the-badge
[forks-url]: https://github.com/P1ayer-1/DeepThought-Engine/network/members
[stars-shield]: https://img.shields.io/github/stars/P1ayer-1/DeepThought-Engine.svg?style=for-the-badge
[stars-url]: https://github.com/P1ayer-1/DeepThought-Engine/stargazers
[issues-shield]: https://img.shields.io/github/issues/P1ayer-1/DeepThought-Engine.svg?style=for-the-badge
[issues-url]: https://github.com/P1ayer-1/DeepThought-Engine/issues
[license-shield]: https://img.shields.io/github/license/P1ayer-1/DeepThought-Engine.svg?style=for-the-badge
[license-url]: https://github.com/P1ayer-1/DeepThought-Engine/blob/master/LICENSE
