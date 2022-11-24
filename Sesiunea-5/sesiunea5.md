# In aceasta sesiune vom rezolva subiectele ce au fost date la bacalaureat 2022

## Subiectul I
1. c
2. d
3. a
4. b
5. c
## Subiectul II
1.
 - a. 4
 - b. 11, 13
 - c.
    ```c++
        #include <iostream>

        using namespace std;
        int main() {
            int n, i = 2, k = 0;
            cin >> n;
            while ( n >= i) {
                while (n % i == 0) {
                    k = k + 1;
                    n = n / i;
                }
                if (i == 2) {
                    i = i + 1;
                } else {
                    i = i + 2;
                }
            }
            cout << k;
            return 0;
        }
    ```
    d. 
    ```json
        citeste n
        i <- 2; k <-0
        cat timp n>= i executa
            daca n % i = 0 atunci
                repeta
                    k <- k+1
                    n <- [n/i]
                pana cand n % i != 0
            daca i = 2 atunci i <- i + 1
            altfel i <- i + 2
        scrie k
    ```
2. Oricare 2 numere dintre urmatoarele: 2022, 2023, 2024, 2025
3. 
- Solutie 1:
    ```c++
        char s[51], char id[51];
        // pch va contine prenumele (e.g Ana)
        char* pch = strtok(s, " ");
        // pch va contine numele (e.g Popescu)
        pch = strtok(NULL, " ");
        strcpy(id, pch);
        strcat(id, "2022");
    ```
- Solutie 2:
    ```c++
        char s[51], char id[51];
        // Facem +1 ca sa nu copiem si spatiul ce separa numele
        strcpy(id, strchr(s, ' ')+1);
        strcat(id, "2022");
    ```
## Subiectul III

1. Solutie:
    ```c++
    #include <iostream>
    #include <cmath>
    using namespace std;

    void secventa(int& n);


    int main()
    {
    int n = 202233228;
    secventa(n);
    cout << n;
    }

    void secventa(int& n) {
        int result =0;
        int pozitii = 0;
        while (n > 0) {
            int ultimaCifra = n % 10;
            n = n / 10;
            int urmatoareaCifra = n % 10;
            if (ultimaCifra == 2 && urmatoareaCifra == 2) {
                result = 20 * pow(10, pozitii) + result;
                n /= 10;
                pozitii = pozitii + 2;
            } else {
                result = ultimaCifra * pow(10, pozitii++) + result;
            }
        }

        n = result;
    }

    ```
2. 