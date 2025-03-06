#include <iostream>
using namespace std;

int main() {
    int A, B, numeroScelto;
    
    // Chiediamo i valori di A e B
    cout << "Inserisci il valore di A: ";
    cin >> A;
    cout << "Inserisci il valore di B: ";
    cin >> B;
    
    // Verifica che A sia minore di B, altrimenti scambia i valori
    if (A > B) {
        cout << "A è maggiore di B, scambio i valori." << endl;
        swap(A, B);
    }
    
    // Chiediamo all'utente di inserire un numero tra A e B
    do {
        cout << "Inserisci un numero tra " << A << " e " << B << ": ";
        cin >> numeroScelto;
        
        if (numeroScelto < A || numeroScelto > B) {
            cout << "Numero non valido. Riprova." << endl;
        }
    } while (numeroScelto < A || numeroScelto > B);
    
    // Alla fine, restituiamo il numero scelto
    cout << "Hai scelto il numero: " << numeroScelto << endl;

    return 0;
}
