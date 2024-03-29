# Exercitii cu functii ce manipuleaza siruri de caractere

1.
    - Sursa: Bac 2012 August, Subiectul 2, exercitiul 4
    - Enunt: 
        - Se consideră două şiruri de caractere a, de lungime na şi b, de lungime nb. Şirul a este numit sufix al şirului b dacă na≤nb şi subşirul lui b determinat de ultimele sale  na caractere coincide cu a. În  secvenţa  de  instrucţiuni  de  mai  jos  variabila  i  este  de  tip  întreg,  iar  variabila  s memorează un şir cu cel mult 20 de caractere. Fără a utiliza alte variabile, scrieţi una sau mai multe instrucţiuni care pot înlocui punctele de suspensie astfel încât, în urma executării secvenţei obţinute, să se afişeze pe ecran, în ordinea  descrescătoare  a  lungimii,  separate  prin  câte  un  spaţiu,  toate  sufixele  şirului memorat în variabila s, ca în exemplu
        - 
            ```json
                Exemplu: pentru şirul elevi se afişează: elevi levi evi vi i 
                for(i=0;i<strlen(s);i++) 
                .................
            ```
    - Solutie:
        ```c++
            #include <iostream>
            #include <cstring>

            using namespace std;

            int main() {
                char s[20] = "elevi";
                int i;
                for ( i = 0; i < strlen(s);i++) {
                    cout << s+i << " ";
                }
                return 0;
            }
        ```

2. 
    - Sursa: Bac 2012 Iunie, Subiectul II, Exercitiul 1
    - Enunt:
        - Expresia `strlen("bine")` are valoarea:
    - Variante:
        * a. 1
        * b. 4 [`CORECT`]
        * c. 5
        * d. 6

3. 
    - Sursa: Bac 2013 August, Subiectul II, Exercitiul 5.
    - Enunt:
        - Se  consideră  un  text  cu  cel  mult  100  de  caractere  (litere  mici  ale  alfabetului  englez  şi spaţii),  în  care  cuvintele  sunt  separate  prin  unul  sau  mai  multe  spaţii.  Înaintea  primului cuvânt şi după  ultimul cuvânt nu există spaţiu. Scrieţi un program C/C++ care citeşte de la tastatură un text de tipul menţionat mai sus şi determină transformarea acestuia în memorie prin eliminarea unor spaţii, astfel încât între 
    oricare  două  cuvinte  alăturate  să  rămână  exact  un  spaţiu.  Programul  afişează  pe  ecran 
    textul obţinut.
    Exemplu:pentru textul 
        ```json
            "in  vacanta    plec la         mare"
            se obţine şi se afişează 
            "in vacanta plec la mare"

    - Solutie:
        ```c++
            #include <iostream>
            #include <cstring>

            using namespace std;

            int main() {
                // Aici initializam rezultat cu "" ca sa putem folosi direct strcat, sa concatenam
                // fiecare cuvant extras din textul initial
                char text[101], rezultat[101]="";
                cin.getline(text, 101);
                char *cuvant = strtok(text, " ");
                while (cuvant != NULL) {
                    strcat(rezultat, cuvant);
                    strcat(rezultat, " ");

                    cuvant = strtok(NULL, " ");
                }

                cout << rezultat;
                return 0;
            }

        ```

4.
    - Sursa: Bac 2014 iunie, Subiectul II, exercitiul 2
    - Enunt: 
        - Variabila `s` poate memora un sir cu maximum 20 de caractere. In urma executarii secventie de instructiuni alaturate se afiseaza:
        ```c++
            strcpy(s, "1b2d3")
            s[2] = 'a' + 2;
            strcpy(s, s+1);
            strcpy(s+3, s+4);
            cout << s; | printf("%s", s);
        ```
    - Variante:
        * a. 1b438
        * b. 1bcd8
        * c. ba2
        * d. bcd [`CORECT`] Atentie la ce anume se suprascrie si la pozitia de unde se copiaza, daca este in afara sau nu  a sirului.

5. 
    - Sursa: Bac 2014 august, Subiectul II, Exercitiul 4
    - Enunt:
        ```json
            Variabila  s  poate  memora  un  șir  cu  maximum  20  de  caractere,  iar  variabila  i  este  de  tip întreg. Scrieți ce se afișează în urma executării secvenței de instrucțiuni de mai jos.  
        ```
        ```c++
        strcpy(s,"BACALAUREAT"); 
        cout<<strlen(s);  |  printf("%d",strlen(s)); 
        i=0; 
        while (i<strlen(s)-1) 
        { if(strchr("EAIOU",s[i])!=NULL) strcpy(s+i+1,s+i+2); 
        i++; 
        } 
        cout<<s;  |  printf("%s",s);
        ```
    - Solutie:
        ```json
                -> i = 0 = consoana, merem mai departe
                -> i = 1 => vocala => S = BACALAUREAT si inlocuim de la pozitia i+1 adica 2 cu textul din s de la pozitia i+2 adica 3
                                      =>s = BAALAUREAT
                -> i = 2 = vocala => si inlocuim de la pozitia i+1 adica 3, cu textul din s de la pozitia i+2 adica 4
                                      => BAAAUREAT
                -> i = 3 => vocala => si inlocuim de la pozitia i+1 adica 4, cu textul din s de la pozitia i+2 adica 5
                ->                  => BAAAREAT
                -> i = 4 => consoana, mergem mai departe
                -> i = 5 => vocala => si inlocuim de la pozitia i+1 adica 6, cu textul din s de la pozitia i+2 adica 7
                              => BAAARET
                -> i = 6 -> ne oprim deoarece i < strlen(s)-1 devine falsa
                -> deci programul afiseaza 11BAAARET
            
        ```