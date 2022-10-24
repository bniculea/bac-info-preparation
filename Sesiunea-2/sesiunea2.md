# Algoritmi elementari

## I. Algoritmi care prelucreaza cifrele unui numar

- Spargerea in cifre a numarului n si prelucrarea cifrelor de la dreapta la stanga
```c++
    while (n) {
        // Extrager ultima cifra
        int lastDigit = n % 10;

        // Eliminare ultima cifra din numar
        n = n / 10;
    }
```

- Spargerea in cifre a numarului n si prelucrarea cifrelor de la stanga la dreapta
```c++
    int positions = 1;
    // Aflam numarul de cifre din numarul initial
    while ((positions * 10) <= n) {
        positions = positions * 10;
    }

    // Cat timp contorul ce contine numarul de cire > 0
    while (positions != 0) {
        // Extragem prima cifra
        int firstDigit = n / positions;

        // Taiem din n prima cifra
        n = n % p;

        // Taiem din p o pozitie, deoarece am extras numarul
        positions = positions / 10;
    }
   
```
### IMPORTANT: Spargerea in cifre a unui numar distruge valoarea initiala a acestuia! Este necesara crearea unei copii a lui `n`, inainte de a se efectua extragerea cifrelor, asta in cazul in care mai avem nevoie de valoarea initiala.

## Exemple de algoritmi ce folosesc spargerea pe cifre:

1. Construirea oglinditului si verificare `n` daca este palindrom
    ```c++
        int isPalindrom(int n) {
        // Facem o copie lui N deoarece avem nevoie de valoarea initiala
        int copieN = n;
        // Initializam oglindit la 0
        int oglindit = 0;

        while (copieN > 0) {
            // Extragem ultima cifra din numar
            int ultimaCifra = copieN % 10;

            // Il adaugam la oglindit, de aceea avem nevoie
            // de  inmultirea cu 10, deoarece ne mutam o pozitie mai la stanga (unitati, zeci, sute, etc)
            oglindit = oglindit * 10 + ultimaCifra;

            // Taiem  ultima cifra din copie
            copieN = copieN / 10;
        }

        // Daca oglinditul este egal cu valoarea initiala
        // Inseamna ca avem un palindrom
        return oglindit == n;
    }
    ```

2. Media aritmetica a cifrelor nenule
    ```c++
        float medieNumereNenule(int n) {
            // Declaram suma float ca sa evitam truncherea la int
            float suma = 0.0;
            int contorCifreNenule = 0;
            while (n > 0) {
                int ultimaCifra = n % 10;
                // Daca ultima cifra este mai mare ca 0
                // Actualizam suma si contorul de cifre nenule
                if (ultimaCifra > 0) {
                    suma = suma + ultimaCifra;
                    contorCifreNenule++;
                }
                
                n = n / 10;
            }
            // In cazul in care avem cel putin o cifra nenula
            // Calculam media
            if (contorCifreNenule > 0) {
                return suma / contorCifreNenule;
            }
            // Altfel inseamna ca avem un numar = 0
            else {
                return 0;
            }
        }
    ```
3. Cifra maxima din `n`
    ```c++
        int cifraMaxima(int n) {
            int maxim = 0;
            while (n > 0) {
                int lastDigit = n % 10;
                if (lastDigit > maxim) {
                    maxim = lastDigit;
                }

                n = n / 10;
            }

            return maxim;
        }

    ```
4. Eliminarea cifrelor impare din `n`
    ```c++
    int eliminareCifreImpare(int n) {
        // Varibila pentru a tine numarul nou format prin eliminarea
        // cifrelor impare
        int numarNou = 0;
        // Variabila pentru a contoriza pozitia unitatilor, zecilor, etc.
        int pozitie = 1;
        while (n > 0) {
            int ultimaCifra = n % 10;
            // Daca ultima cifra este para, o extragem si o adaugam la numarul nou
            if (ultimaCifra % 2 == 0) {
                // Numarul nou devine valoarea precedenta +
                // ultimaCifra inmultita cu pozitia
                numarNou = numarNou + ultimaCifra * pozitie;
                pozitie = pozitie * 10;
            }

            // Eliminare ultima cifra
            n = n / 10;
        }

        return numarNou;
    }
    ```
    - NOTA: Daca se doreste eliminarea cifrelor pare, tot ce trebuie sa facem va fi sa modificam conditia din:
        - `ultimaCifra %2 == 0` in ` ultimaCifra %2 != 0`

5. Dublarea aparitiilor cifrelor pare din `n`
    ```c++
        int dublareAparitiiCifrePare(int n) {
            // Variabila pentru a tine numarul nou. Practic recreem numarul, si dublam cifra in cazul in care aceasta este para.
            int numarNou = 0;
            // Variabila pentru a contoriza pozitia unitatilor, zecilor, etc.
            int pozitie = 1;
            while (n > 0) {
                int ultimaCifra = n % 10;
                // Daca ultima cifra este para
                if (ultimaCifra % 2 == 0) {
                    // Noul numar are valoare ultimaCifra * pozite + vechea valoare
                    numarNou = numarNou + ultimaCifra * pozitie;
                    // Pozitia se muta mai la stanga
                    pozitie = pozitie * 10;
                }
                // In cazul in care ultima cifra nu este para
                // Tot adaugam ultima cifra la numarul nou. Insa daca este para, aceasta este adaugata de 2 ori.
                numarNou = numarNou + ultimaCifra * pozitie;

                // Incrementam pozitia
                pozitie = pozitie * 10;

                // Eliminam ultima cifra
                n = n / 10;
            }

            return numarNou;
        }
    ```

6. Numararea cifrelor pare existente in `n`
    ```c++
        int numarareCifrePare(int n) {
            // Initializare contor pentru cifre pare
            int contorCifrePare = 0;
            while (n > 0) {
                // Extragem ultima cifra para
                int ultimaCifra = n % 10;
                if (ultimaCifra % 2 == 0) {
                    contorCifrePare++;
                }
                
                n = n / 10;
            }

            return contorCifrePare;
        }
    ```
7. Cifra de control a unui numar `n` se obtine calculand suma cifrelor lui `n` apoi repetand procesul cu cifrele sumei obtinute anterior pana cand se obtine un numar format dintr-o singura cifra, numita `cifra de control`.
    - De exemplu, pentru n = 8579 se obtin pe rand sumele:
        - 8 + 5 + 7 + 9 = 29
        - 2 + 9 = 11
        - 1 + 1 = 2 (`cifra de control`)
- Algoritmul eficient ca timp de executie se bazeaza pe observatia ca cifra de control a unui numar respecta urmatoarea relatie:
    - cifraControl(n) = 
        - 0, daca `n` = 0
        - 9, daca `n` % 9 = 0 si `n` != 0
        - n % 9, altfel
    ```c++
        int cifraControl(int n) {
            while (n > 9) {
                int sumCifra = 0;
                while (n != 0) {
                    int ultimaCifra = n % 10;
                    sumCifra = sumCifra + ultimaCifra;
                    n = n / 10;
                }
                n = sumCifra;
            }
            return n;
        }
    ```

## II. Divizibilitate. Algoritmi care prelucreaza divizorii proprii/improprii/primi ai unui numar.
