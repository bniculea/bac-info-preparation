# Varianta 6

## Subiectul I
1. a (ATENTIE!!! => operatorii aritmetici +,-,*,/) au prioritate mai mare decat operatorii relationali
2. b
3. d (un graf este complet dacă numărul total de muchii este n(n-1)/2)
4. b (Se genereaza numerele: 1010, 1012, 1014, 1030, 1032, 1034, etc, al 4-lea numar fiind 1030)
5. b
## Subiectul II
1. 
    a. Se vor afisa numerele: `34, 100, 50`
    b. 
        ```json
            Algoritmul afiseaza maximul dintr-o secventa.
            Un alt exemplu ar putea fi: 21 4 5 6 0 7 8 21 8 8 0 11 15 17 21 0 0
        ```
    c.
        ```json
            citeste a,b (numere naturale nenule)
            m a
            ┌dacă a>0 sau b>0 atunci
            | ┌repeta
            | | a b
            | | citeste b
            | | ┌dacă a>m atunci
            | | |m a
            | | └■
            | | ┌dacă b=0 și a>0 atunci
            | | | scrie m
            | | | m 0
            | | └■
            | └ până când a<=0 și b<=0
            └■
        ```
    d.
        ```c++
            #include <iostream>

            using namespace std;
            int main(){
                int a, b, m;
                cin >> a >> b;
                m = a;
                while (a > 0 || b > 0) {
                    a = b;
                    cin >> b;
                    if (a > m) {
                        m = a;
                    }
                    if (b == 0 && a > 0) {
                        cout << m;
                        m = 0;
                    }
                }
            }

        ```
2. Solutie:
    ```c++
        #include <iostream>
        using namespace std;

        struct data
        {
            int zi,luna,an;
        };
        struct elev
        {
            char nume[20];
            data datan;
        };
        elev m;

        int main() {

            cout << "Introduceti numele elevului (max 20 caractere): ";
            cin.getline(m.nume, 20);
            cout << "Introduceti data nasterii\n";
            cout << "Ziua: ";
            cin >> m.datan.zi;
            cout << "Luna: ";
            cin >> m.datan.luna;
            cout << "Anul: ";
            cin >> m.datan.an;

            if (m.datan.an < 2000) {
                cout << m.nume;
            }  else {
                cout << m.datan.zi <<"/"<<m.datan.luna<<"/"<<m.datan.an;
            }
            return 0;
        }

    ```
3. Solutie: `bacalaureat`. Programul transforma literele mari in litere mici.
## Subiectul III