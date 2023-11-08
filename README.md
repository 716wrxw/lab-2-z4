#include <iostream>
#include <string>
#include <bitset>

// Функція для зсуву бітів рядка вліво на певну величину
std::string cyclicLeftShift(const std::string& text, int shift) {
    std::string shiftedText = text;
    int length = text.length();

    // Виконуємо зсув для кожного символу
    for (int i = 0; i < length; i++) {
        char c = text[i];
        // Зсуваємо біти символу вліво на вказану кількість разів
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
