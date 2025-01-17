### Stefan Diana Maria - 332CC
# Desenarea paralela de curbe contur folosind algoritmul Marching Squares

- Am combinat functiile `rescale_image`, `sample_grid` si `march` intr-o functie `func`, de tip *void**, care este apelata pe fiecare thread. 
- Argumentele necesare functiei sunt transmise printr-un element al vectorului de tip `arg_func_wrapper`, care contine id-ul threadului curent si un pointer catre `args` (de tip `arg_func`). `args` contine toate argumentele necesare functiilor initiale, bariera si numarul de threaduri.

## Paralelizarea programului 
- Pentru fiecare `for` au fost impartite calculele la numarul de threaduri, prin calcularea unui `start` si `end` unic fiecarui thread. 
- Pentru instructiunile ce trebuie repetate o singura data (alocarile si eliberarile de memorie), am folosit threadul cu id-ul 0, urmate de o bariera.
- Am folosit `bariera` unde era necesara terminarea operatiilor anterioare pentru a continua.

> [!IMPORTANT]
> `in_6.ppm` si `in_7.ppm` au dimensiuni prea mari. Se gasesc in arhiva!
