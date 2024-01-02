# Rezolvare varianta 7 din cartea lui Vlad
1. 
    - Rezolvare
        * Din enunt stim ca avem 2 intervale care nu se intersecteaza (atentia la intervale)
            * De exemplu a = 1 si b = 3, si c= 5 si d= 8
        * Acum haideti sa luam fiecare optiune si sa gasim pe cea corecta
            * a -> Aici putem sa obtinem 1 (adevarat) si daca intersectia intervalelor nu este vida deci optiunea nu este corecta
                * de exemplu a = 2, b = 3, c = 1, d = 6
            * b -> Din nou, si aici putem sa obtinem 1 (adevarat) si daca intersectia intervalelor nu este vida deci optiunea nu este corecta
                * de exemplu a = 3, b = 6, c = 3, d = 8
            * c -> Acesta optiune cade deoarece stim ca numerele au proprietatea ca a <=b si c<=d. Si din ce vedem in optiune, daca a>d, rezulta implicit ca a >=c deci prin urmare b nu poate sa fie mai mic decat c, deoarece b este cel putin egal cu a
            * d -> Optiunea este adevarata deoarece conform proprietatii si conditiei din enunt, obtinem 1 (adevarat) doar daca se respecta conditia din enunt si proprietatea celor 4 numere
                * de exemplu a = 2, b = 4, c = 4 d = 7 si aici vedem ca (a, b) nu se intersecteaza cu [c,d]
    - Raspuns corect: `d`
2. 
    - Rezolvare:
        ```json
            scrie(2021, 2023) = 
                scrie (2022, 2023) =
                    = scrie (2023, 2023)
                        = afiseaza: "2023 2023"
        ```
        - Raspuns corect: `c`
3. 
    - Rezolvare:
        - Conform enuntului stim ca avem combinatii de forma:
            - `_ _ _ _ _ Lebada`
            - Mai stim ca leul tigrul si ursul nu pot sa fie vecini cu cerbul Asa ca o sa avem doua situatii:
                1. punem cerbul pe prima pozitie si lebada pe ultima. Asta automat inseamna ca o sa punem papagalul pe a doua pozitie si o sa restrangem combinatiile la forma:
                    - `Cerb Papagal _ _ _ Lebada`
                2. Punem cerbul intre papagal si lebada asta insemnand ca avem combinatii de forma:
                    - `_ _ _ Papagal Cerb Lebada`
            - Acum stim ca cele 3 locuri libere in ambele situatii pot fi alocate catre leu, tigru si urs astfel:
                - Leu Tigru Urs
                - Leu Urs Tigru
                - Tigru Leu Urs
                - Tigru Urs Leu
                - Urs Leu Tigru
                - Urs Tigru Leu
            - In concluzie avem 6 posibile combinatii pentru fiecare situatie, deci in total `12`
        - Raspuns corect `d`

4. 
    - Rezolvare:
        - Conform enuntului stim ca avem 2022 de varfuri si 1000 de muchii.
        - 1000 de muchii inseamna ca automat avem 1000 de valori `1` in matrice. Faptul ca este neorientat, dubleaza acest numar la 2000 deoarece daca, sa zicem varful 1 este conectat cu varful 3, in matrice o sa avem `1` atat pentru muchia `(1,3)` cat si pentru muchia `(3,1)`
    - Raspuns corect: `c`
5. 
    - Rezolvare:
        * a -> Fals deoarece arborele este un graf conex aciclic
        * b-> Fals deoarece eliminand o muchie, cel putin un nod va deveni izolat, deci conexitatea va fi eliminata
        * c -> Adevarat, conform teoriei, arborele este un graf conex cu n-1 muchii [https://www.pbinfo.ro/articole/5982/arbori-cu-radacina]
        * d -> Fals, acelasi lucru ca la a
    - Raspuns corect `c`
## Subiectul I

## Subiectul II

## Subiectul III