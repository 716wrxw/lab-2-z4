#include <iostream>
#include <string>
#include <bitset>


std::string cyclicLeftShift(const std::string& text, int shift) {
    std::string shiftedText = text;
    int length = text.length();


    for (int i = 0; i < length; i++) {
        char c = text[i];
       
        shiftedText[i] = text[(i + shift) % length];
    }

    return shiftedText;
}

int main() {
    std::string inputText;
    int shiftAmount;

    std::cout << "Введіть текст для шифрування: ";
    std::getline(std::cin, inputText);

    std::cout << "Введіть кількість позицій для циклічного зсуву: ";
    std::cin >> shiftAmount;

    // Виконуємо циклічний зсув ліворуч
    std::string shiftedText = cyclicLeftShift(inputText, shiftAmount);

    std::cout << "Зашифрований текст: " << shiftedText << std::endl;

    return 0;
}
