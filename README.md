# Exercicio 1

```cpp
#include <iostream>

using namespace std;

char *strchr(char *s, char ch) {
    for (int i = 0; s[i] != '\0'; i++) {
        if (s[i] == ch) {
            return &s[i];
        }
    }
    // Resultado caso o ponteiro não foi encontrado
    return nullptr;
}

int main() {
    cout << "Escreva uma palavra ou frase: ";
    char *str = new char[100];
    cin >> str;
    cout << "Digite uma letra que possa ou não estar presenta na frase: ";
    char ch;
    cin >> ch;
    char *result = strchr(str, ch);
    if (result != nullptr) {
        cout << "A letra " << ch << " esta presente na frase." << endl;
        cout << "Ponteiro atribuido a " << ch << ": " << &result << endl;
    } else {
        cout << "A letra " << ch << " não está presente na frase." << endl;
    }
}
```

# Exercicio 2

```cpp
#include <iostream>

using namespace std;

int strlen(char *str) {
    int i = 0;
    while (str[i] != '\0') {
        i++;
    }
    return i;
}

char* end(char *str, char *orig) {
    int strLen = strlen(str);
    int origLen = strlen(orig);

    char *elements = new char[strLen + origLen];

    for (int i = 0; i < strLen; i++) {
        elements[i] = str[i];
    }

    for (int i = 0; i < origLen; i++) {
        elements[strLen + i] = orig[i];
    }

    return elements;
}

char* delupper(char *str) {
    int strLen = strlen(str);

    char *ptr = new char[strLen];

    int pi = 0;

    for (int i = 0; str[i] != '\0'; i++) {

        if (str[i] >= 'A' && str[i] <= 'Z') continue;

        ptr[pi] = str[i];
        pi++;
    }

    cout << ptr << endl;

    return ptr;
}

int cchar(char *str, char *c) {
    int strLen = strlen(str);

    int o = 0;

    for (int i = 0; i < strLen; i++) {
        if (str[i] == c[0]) o++;
    }

    return o;
}

int cvowels(char *str) {
    int strLen = strlen(str);

    int o = 0;

    for (int i = 0; i < strLen; i++) {
        if (str[i] == 'a' || str[i] == 'e' || str[i] == 'i' || str[i] == 'o' || str[i] == 'u') o++;
    }

    return o;
}
```
