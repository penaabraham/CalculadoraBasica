#include <iostream>
#include <cstdlib> // Para system("cls")

using namespace std;

float sumar(float a, float b);
float restar(float a, float b);
float multiplicar(float a, float b);
float dividir(float a, float b);

int main() {
    float num1, num2;
    char op, res;
    
    do {
        system("cls"); // Limpiar la pantalla

        cout << "***Calculadora Básica***" << endl;
        cout << "Ingrese el primer número: ";
        cin >> num1;

        cout << "Ingrese el segundo número: ";
        cin >> num2;

        cout << "Ingrese la operación (+, -, *, /): ";
        cin >> op;

        float resultado;

        switch (op) {
            case '+':
                resultado = sumar(num1, num2);
                break;
            case '-':
                resultado = restar(num1, num2);
                break;
            case '*':
                resultado = multiplicar(num1, num2);
                break;
            case '/':
                resultado = dividir(num1, num2);
                break;
            default:
                cout << "Error: Opción no válida." << endl;
                resultado = 0; // Establecer el resultado a 0 en caso de error
        }
        
        cout << "El resultado es: " << resultado << endl;
        cout << endl << "Regresar al menú (s/n): ";
        cin >> res;
    } while (res == 's' || res == 'S');

    return 0;
}

float sumar(float a, float b) {
    return a + b;
}

float restar(float a, float b) {
    return a - b;
}

float multiplicar(float a, float b) {
    return a * b;
}

float dividir(float a, float b) {
    if (b != 0) {
        return a / b;
    } else {
        cout << "Error: No se puede dividir entre cero." << endl;
        return 0;
    }
}
