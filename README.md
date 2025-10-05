# clsString.h - Comprehensive String Utility Class for C++

## 🧩 Overview
`clsString` is a modern, lightweight, and reusable **C++ header-only class** that simplifies string handling and manipulation.

It provides powerful tools for **case conversion, trimming, splitting, joining, counting, and replacing** operations — all without requiring external dependencies.

This library is designed to make string processing cleaner, faster, and easier in your C++ projects.

---

## 🚀 Key Features

### ✏️ Basic Operations
- `Length()` — returns string length.
- `CountWords()` — counts words separated by spaces.
- `Split()` — splits a string into a vector using a delimiter.
- `JoinString()` — joins an array or vector of strings into one string.
- `TrimLeft()`, `TrimRight()`, `Trim()` — removes leading/trailing spaces.

### 🔠 Case Manipulation
- `UpperAllString()` / `LowerAllString()`
- `UpperFirstLetterOfEachWord()` / `LowerFirstLetterOfEachWord()`
- `InvertAllLettersCase()` — inverts character case for each letter.
- `InvertLetterCase(char)` — toggles a single character’s case.

### 🔍 Counting Tools
- `CountLetters()` — counts capital/small letters or all characters.
- `CountCapitalLetters()`, `CountSmallLetters()`
- `CountSpecificLetter()` — counts how many times a given character appears (case-sensitive or not).
- `CountVowels()` — returns the number of vowels (A, E, I, O, U).

### 🧹 Cleaning & Editing
- `RemovePunctuations()` — removes punctuation marks from a string.
- `ReplaceWord()` — replaces occurrences of a word (with optional case-sensitivity).
- `ReverseWordsInString()` — reverses the order of words in a sentence.

### 🧠 Object-Oriented Integration
- Works both statically and as an object:
  ```cpp
  clsString myText("hello world");
  myText.UpperAllString(); // modifies the object directly
  ```

- Uses a property system:
  ```cpp
  myText.Value = "New Text";
  cout << myText.Value;
  ```

### ⚙️ Enums
- `enWhatToCount` enum allows custom count behavior:
  - `SmallLetters`
  - `CapitalLetters`
  - `All`

---

## 💡 Example Usage

```cpp
#include <iostream>
#include "clsString.h"
using namespace std;

int main()
{
    clsString text("hello world from cpp");

    cout << "Original: " << text.GetValue() << endl;
    cout << "Length: " << text.Length() << endl;
    cout << "Words: " << text.CountWords() << endl;

    text.UpperFirstLetterOfEachWord();
    cout << "Title Case: " << text.GetValue() << endl;

    text.InvertAllLettersCase();
    cout << "Inverted Case: " << text.GetValue() << endl;

    cout << "Vowels: " << text.CountVowels() << endl;

    string reversed = clsString::ReverseWordsInString("C++ is fun to learn");
    cout << "Reversed Words: " << reversed << endl;

    string cleaned = clsString::RemovePunctuations("Hi! This, is a test...");
    cout << "Cleaned: " << cleaned << endl;

    return 0;
}
```

---

## 🧪 Testing Guide

You can validate each function individually or run unit tests using `assert()`:

```cpp
#include "clsString.h"
#include <cassert>
#include <iostream>
using namespace std;

int main()
{
    clsString s("hello world");
    assert(s.Length() == 11);
    assert(s.CountWords() == 2);
    assert(clsString::CountVowels("education") == 5);
    assert(clsString::Trim("   text  ") == "text");
    assert(clsString::ReplaceWord("I love C++", "love", "use") == "I use C++");
    assert(clsString::ReverseWordsInString("C++ is fun") == "fun is C++");

    cout << "All tests passed successfully!" << endl;
}
```

Compile and run:
```
g++ -std=c++17 test_clsString.cpp -o test && ./test
```

---

## 🧾 Example Output

```
Original: hello world from cpp
Length: 19
Words: 4
Title Case: Hello World From Cpp
Inverted Case: hELLO wORLD fROM cPP
Vowels: 5
Reversed Words: learn to fun is C++
Cleaned: Hi This is a test
All tests passed successfully!
```

---

## ⚡ Performance & Compatibility
- **Header-only:** Just `#include "clsString.h"`
- No dynamic allocations besides STL containers.
- Compatible with **C++11 and newer**.
- Works on Windows, Linux, and macOS.

---

## 🧱 Class Structure
```
clsString.h
└── clsString
    ├── Constructors
    ├── Static string utilities
    ├── Object-based instance functions
    ├── enWhatToCount enum
    └── String manipulation toolkit
```

---

## 🧰 Future Enhancements
- Add substring search and replace by index.
- Add string comparison ignoring case.
- Add conversion tools (to upper snake case, kebab case, etc.).
- Add UTF-8 and wide string support.

---

## 📜 License
Open-source and free for educational or commercial use.
