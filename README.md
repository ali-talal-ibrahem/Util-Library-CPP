 
# 🧰 clsUtil Library for C++

## Overview 🎯

The `clsUtil` library is a collection of general-purpose helper functions for C++ applications. It simplifies common tasks such as random value generation, key creation, filling and shuffling arrays, swapping values across multiple types, and simple text encryption/decryption. The library also uses `clsDate` for some date-related utilities.

## Features ✨

- **Random seed initialization**: `Srand()` to seed the RNG once.
- **Random number generation**: `RandomNumber(From, To)`.
- **Character and word generation**: `GetRandomCharacter()`, `GenerateWord()`.
- **Key generation**: `GenerateKey()` to produce keys like AAAA-BBBB-CCCC-DDDD.
- **Array utilities**: functions to fill arrays with random numbers, words, or keys.
- **Swap helpers**: `Swap` overloads for `int`, `double`, `string`, `char`, `bool`, and `clsDate`.
- **Array shuffling**: `ShuffleArray(...)` to shuffle elements.
- **Text helpers**: `Tabs()` to generate tab strings, `EncryptText()` and `DecryptText()` for simple text obfuscation.

## Installation 📦

1. Place `clsUtil.h` in your project folder.
2. To use the library correctly you must include the ClsDate library from the following link:

   https://github.com/ali-talal-ibrahem/Date-Library-CPP

3. Then include the header in your source files:

```cpp
#include "clsUtil.h"
```

> Note: `clsUtil.h` includes `clsDate.h`, so make sure `clsDate.h` is available in the same folder or adjust your include paths.

## Usage Example 💡

```cpp
#include <iostream>
#include "clsUtil.h"

using namespace std;

int main() {
    clsUtil::Srand();

    cout << "Random number: " << clsUtil::RandomNumber(1, 100) << endl;
    cout << "Random key: " << clsUtil::GenerateKey() << endl;

    string arr[100];
    clsUtil::FillArrayWithRandomWords(arr, 5, clsUtil::CapitalLetter, 6);
    clsUtil::ShuffleArray(arr, 5);
    for (int i = 0; i < 5; i++)
        cout << arr[i] << endl;

    // Example of swapping dates (requires clsDate)
    clsDate d1(1,1,2000), d2(2,2,2002);
    clsUtil::Swap(d1, d2);

    return 0;
}
```

## Class Structure 🏗️

### Main Methods:

| Method | Description |
|--------|-------------|
| `Srand()` | Seed the random number generator (call once) |
| `RandomNumber(int From, int To)` | Generate a random integer between two values |
| `GetRandomCharacter(enCharType)` | Get a random character by type |
| `GenerateWord(enCharType, short Length)` | Generate a word with the specified length |
| `GenerateKey()` | Generate a key in the format AAAA-BBBB-CCCC-DDDD |
| `FillArrayWithRandomNumbers(...)` | Fill an array with random numbers |
| `FillArrayWithRandomWords(...)` | Fill an array with random words |
| `FillArrayWithRandomKeys(...)` | Fill an array with random keys |
| `Swap(...)` | Swap values for various types (int, double, string, clsDate, ...) |
| `ShuffleArray(...)` | Shuffle array elements |
| `Tabs(short)` | Generate tab characters as a string |
| `EncryptText(string, short)` | Simple text encryption/obfuscation |
| `DecryptText(string, short)` | Simple text decryption |

## Requirements 📋

- C++ compiler (C++11 or later)
- `clsDate` library (required for date-related swap/operations)

## Dependencies 🔗

- You must include the `clsDate` library from the following link to use date-related features:

  https://github.com/ali-talal-ibrahem/Date-Library-CPP

Make sure `clsDate.h` is placed in the same directory or adjust include paths when building.

## Future Updates 🚀

- Improve key generation options and configuration
- Support additional data types in `Swap`
- Replace simple encryption with a more secure option
- Add unit tests

## Author 👨‍💻

**Ali Talal Ibrahem**

**Date**: May 2, 2026

---

*This library is provided "as-is" for educational and practical use in C++ projects.*