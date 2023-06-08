# Varianta sesiune speciala

## Subiectul I
1. c (Atentie la conditie! Trebuie sa fie 1 doar daca sunt numere pare nu si in alte conditii)
2. a
3. d
4. b
    ```json
        0 1 2 3 4
        A M U R G

        23014 -> URAMG
        23041 -> URAGM
        23104 -> URMAG
        23140 -> URMGA
        23401 -> URGAM


        42310 -> GURMA
        43012 -> GRAMU
    ```
    - Se observa cum numerele generate sunt in ordine crescatoare, astfel obtinem solutia aferenta.
5. 
    - Definitii:
        - drum elementar: Un lant (drum), se numeste `elementar` daca in el nu se repeta noduri.
        - lant: Se numește lanț, în graful G, o succesiune de arce, notată
L = (u1 , u2 ,..., uk) cu proprietatea ca oricare două arce consecutive au o extremitate comună
    - Solutie: `c`
    - Explicatie: `1 -> 2 -> 4 -> 8 -> 16 -> 15 -> 14 -> 13 -> 12 -> 11 -> 22 -> 21 -> 20 -> 19 -> 18 -> 17`
## Subiectul II
1. 
- a: `233223222`
- b: 5 -> va genera: `2333322333222332222322222` deoarece putem observa cum pentru 3, obtinem 9 caractere deci patratul lui 3 (se poate observa asta si din natura celor doua for-uri)
- c
    ```c++
        #include <iostream>
        #include <string.h>
        #include <string>
        using namespace std;

        int main()
        {
            int n;
            cin >> n;
            for (int i = 1; i<=n; i++) {
                for (int j = 1; j<= n; j++) {
                    if (j <= i) {
                        cout << 2;
                    } else {
                        cout << 3;
                    }
                }
            }
            return 0;
        }
    ```
- d:
    ```json
        citeste n (numar natural nenul)
        pentru i<- 1, n executa
            j<- 1
            executa
                daca j<= i atunci
                    scrie 2
                altfel
                    scrie 3
                j++
            cat timp (j<= n)
    ```
2. `4 5 6 7`
3. Solutie:
    ```c++
        #include <iostream>
        #include <string.h>
        #include <string>
        using namespace std;

        int main()
        {
        char s[21];
        cin >> s;
        for (int k = strlen(s)-1;k>= 0; k--) {
            char temp[21];
            strncpy(temp, s, k+1);
            temp[k+1]='\0';
            if (temp[k] == s[0]) {
                cout << temp << " ";
            }
        }
            return 0;
        }

    ```
## Subiectul III
1. Solutie:
    ```c++
        #include <iostream>
        #include <string.h>
        #include <string>
        using namespace std;
        void Putere(int n, int&x, int&p);
        int main()
        {
            int n, x, p;
            cin >> n;
            Putere(n, x, p);
            cout << "x = " << x << "; p= " << p << endl;
            return 0;
        }

        void Putere(int n, int&x, int&p) {
                x = 2;
                while(true) {
                    int rezultatTemporar = x;
                    int putere = 1;
                    while (rezultatTemporar < n) {
                        rezultatTemporar *= x;
                        putere++;
                    }
                    if (rezultatTemporar == n) {
                        p = putere;
                        break;
                    } else {
                        x++;
                    }
                }
        }

    ```
2. 
3. 