#include <iostream>
using namespace std;

void dibujarEstrella4Picos(int altura) {
    // middle part
    // upper middle part
    for (int i = 1; i <= (altura + 3) / 2; ++i) {
        
        for (int j = 1; j <= 3*(i - 1) + 1; ++j)
            cout << " ";
        for (int ast = 3 * (altura + 1); ast >= 3 * (i - 1) + 1 ; --ast)
            cout << "* ";
        cout << "\n";
    }
    
    //Bootom part
    for (int i = 1; i <= (altura + 1) / 2; ++i) {
        for (int j = (2 * altura + 7) / 2; j >= i; --j)
            cout << " ";
        for (int ast = altura; ast > 2 * (i - 1); --ast )
            cout << "* ";
        for (int sp = 1; sp <= 10 * (i - 1) + 2; ++sp)
            cout << " ";
        for (int ast = altura; ast > 2 * (i - 1); --ast )
            cout << "* ";  
             cout << "\n";
    }
}

void dibujarEstrella5Picos(int altura) {
     //top part
    for (int i = 1; i <= altura; ++i) {
        
        for (int j = 1; j <= 2*(altura + 2); ++j)
            cout << " ";
        for (int j = altura; j > i ; --j)
            cout << " ";
        for (int ast = 1; ast <= i; ++ast)
            cout << "* ";
        cout << "\n";
    }
    
    // middle part
    // upper middle part
    for (int i = 1; i <= (altura + 3) / 2; ++i) {
        
        for (int j = 1; j <= 3*(i - 1) + 1; ++j)
            cout << " ";
        for (int ast = 3 * (altura + 1); ast >= 3 * (i - 1) + 1 ; --ast)
            cout << "* ";
        cout << "\n";
    }
    // Lower middle part
    for (int i = 1; i <= altura/2 - 1; ++i) {
        for (int j = 3 * (altura + 1) / 2 ; j >= i ; --j)
            cout << " ";
        for (int ast = 1; ast <= (3 * altura + 3) / 2 + i; ++ast)
            cout << "* ";
        cout << "\n";
    }
    
    //Bootom part
    for (int i = 1; i <= (altura + 1) / 2; ++i) {
        for (int j = (2 * altura + 7) / 2; j >= i; --j)
            cout << " ";
        for (int ast = altura; ast > 2 * (i - 1); --ast )
            cout << "* ";
        for (int sp = 1; sp <= 10 * (i - 1) + 2; ++sp)
            cout << " ";
        for (int ast = altura; ast > 2 * (i - 1); --ast )
            cout << "* ";  
             cout << "\n";
    }
}

void dibujarEstrella6Picos(int altura) {
    for (int i = 0; i < altura; i++) {
        for (int j = 0; j < altura - i; j++) {
            cout << " ";
        }
        for (int j = 0; j < 2 * i + 1; j++) {
            cout << "*";
        }
        cout << endl;
    }

    for (int i = altura - 2; i >= 0; i--) {
        for (int j = 0; j < altura - i; j++) {
            cout << " ";
        }
        for (int j = 0; j < 2 * i + 1; j++) {
            cout << "*";
        }
        cout << endl;
    }
}

int main() {
    int opcion, altura;
    char continuar;

    do {
        cout << "Seleccione una opción:" << endl;
        cout << "1. Estrella de 4 picos" << endl;
        cout << "2. Estrella de 5 picos" << endl;
        cout << "3. Estrella de 6 picos" << endl;
        cout << "4. Salir" << endl;
        cin >> opcion;

        switch (opcion) {
            case 1:
                cout << "Ingrese la altura de la estrella (limite: 10): ";
                cin >> altura;
                if (altura <= 10) {
                    dibujarEstrella4Picos(altura);
                } else {
                    cout << "La altura ingresada supera el límite." << endl;
                }
                break;
            case 2:
                cout << "Ingrese la altura de la estrella (limite: 10): ";
                cin >> altura;
                if (altura <= 10) {
                    dibujarEstrella5Picos(altura);
                } else {
                    cout << "La altura ingresada supera el límite." << endl;
                }
                break;
            case 3:
                cout << "Ingrese la altura de la estrella (limite: 10): ";
                cin >> altura;
                if (altura <= 10) {
                    dibujarEstrella6Picos(altura);
                } else {
                    cout << "La altura ingresada supera el límite." << endl;
                }
                break;
            case 4:
                cout << "Saliendo del programa." << endl;
                break;
            default:
                cout << "Opción no válida." << endl;
        }

        cout << "¿Desea dibujar otra estrella? (s/n): ";
        cin >> continuar;
    } while (continuar == 's' || continuar == 'S');

    return 0;
}
