# Rezolvare model subiect bacalaureat informatica 2023

## Adresa:
- https://www.pbinfo.ro/resurse/9dc152/examene/2023/E_d_Informatica_2023_sp_MI_C_var_model.pdf
- https://www.pbinfo.ro/resurse/9dc152/examene/2023/E_d_Informatica_2023_sp_MI_bar_model.pdf


## Rezolvare

### Subiectul I
1. b
2. d
3. a
4. c
5. Detalii:
    - Se numește ciclu eulerian un ciclu care conține toate muchiile grafului.
    - Se numește ciclu hamiltonian un ciclu elementar care conține toate vârfurile grafului
    - Avem: ciclu eulerian lungime 11 (11 muchii) si ciclu hamiltonian de lungime 7. => 6 noduri
    - Dupa desen, rezulta 5 pot fi sterse => D

### Subiectul II
1. 
    - a: 90
    - b: Oricare doua numere din intervalul [70, 74]
    - c: 
        ```c++
            #include <iostream>
            using namespace std;


            int main()
            {
                int m, n, p, q, s = 0;
                cin >> m >> n >> p >> q;
                for (int x = p; x <=q; x++) {
                    if (x % m == 0 || x % n == 0) {
                        s = s+x;
                    }

                    if (x % m == 0 && x % n == 0) {
                        s = s-x;
                    }
                }
                cout << s;
            }
        ```
    - d
        ```json
            citeste m,n,p,q (numere naturale nenule, p<= q)
            s <- 0
            x<-p
            cat timp (x <= q) executa:
                daca x%m=0 sau x%n=0 atunci
                    s <- s+x;
                daca x%m=0 si x%n=0 atunci
                    s <- s-x
                x++;
            scrie s;
        ```
2. Exemplu cu tot cu sortare + verificare:
    ```c++
        #include <iostream>
        #include <string.h>
        using namespace std;


        struct echipa {
            char nume[50];
            int rezultat;
        };

        int main()
        {
            struct echipa c[3];
            strcpy(c[0].nume, "Bayern");
            c[0].rezultat = 100;

            strcpy(c[1].nume, "Inter");
            c[1].rezultat = 250;

            strcpy(c[2].nume, "Milan");
            c[2].rezultat = 1000;

            for (int i = 0; i < 3; i++) {
                for (int j = 0; j < 2; j++) {
                    if (c[j].rezultat < c[j+1].rezultat) {
                        echipa temp = c[j];
                        c[j] = c[j+1];
                        c[j+1] = temp;
                    }
                }
            }

            for (int i = 0; i < 3; i++) {
                cout << c[i].nume << " ";
            }
        }
    ```
3. 
### Subiectul III