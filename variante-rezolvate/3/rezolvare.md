# Varianta culeasa din culegerea bacalaureat la informatica - Teste Rezolvate (2023) V1

## Subiectul 1.
1. b
2. a
3. c
    - numerele sunt: 2125; 2135; 2145; 2225; 2235; 2245; 2325; 2335; 2345; 2425; 2435; 2445; 2525; 2535; 2545
4. c - Formula este `2 la puterea (n* (n-1))/2`
5. d (deoarece ciclic inseamna sa ai lant simplu insa noi avem un lant elementar)

## Subiectul II
1. 
    - a: 1355
    - b: Programul elimina toate cifrele impare si va returna numarul format din cifrele pare ale acestuia incrementate cu 1.
        - Raspuns: 16, 36, 56, 76, 96, 61, 63, 65, 67, 69
    - c
        - Raspuns:
            ```c++
                citeste n (numar natural)
                z <- 0; p<-1;
                daca n > 0 executa
                    executa
                        c <- n%10; n <- n/10
                        daca c%2 = 0 atunci
                            z <- z + p * (c+1); p <- p * 10
                    cat timp n > 0

                scrie z
            ```
    - d
        ```c++
            #include <iostream>
            #include <cmath>
            using namespace std;
            int main()
            {

                int n, z = 0, p = 1;
                cin >> n;
                while (n > 0) {
                    int c = n % 10;
                    n = n / 10;
                    if (c % 2 == 0) {
                        z = z + p * (c+1);
                        p = p * 10;
                    }
                }
                cout << z;
                return 0;
            }
        ```

2. Raspuns: Vom folosi distanta dintre 2 puncte
    ```c++
        float distantaAO = sqrt((A.x - 0) * (A.x - 0) + (A.y - 0) * (A.y - 0)));
        float distantaBO = sqrt((A.x - 0) * (A.x - 0) + (A.y - 0) * (A.y - 0)));
    ```