# K-Means Clustering con CUDA

Questo progetto implementa l'algoritmo di clustering **K-Means** utilizzando un approccio di layout dati **Structure of Arrays (SoA)**, in linguaggio C++, parallelizzato utilizzando **CUDA** per migliorare le prestazioni su architettura a parallelismo massivo (Massively Parallel Architecture) come le GPU.
In questa implementazione è stato utilizzato Google Colab che fornisce una GPU Tesla T4.

## Descrizione
L'algoritmo K-Means è uno dei più noti metodi di apprendimento non supervisionato per il partizionamento di un set di dati in $K$ gruppi (cluster). 
Questa implementazione sfrutta il parallelismo a livello di thread per velocizzare:
1. Il calcolo delle distanze tra punti e centroidi.
2. L'assegnazione dei punti al cluster più vicino.
3. L'aggiornamento della posizione dei centroidi.

## Prerequisiti
Per compilare ed eseguire il progetto [kmeansCUDA.ipynb](kmeansCUDA.ipynb) in locale sfruttando la propria GPU NVIDIA, è necessario avere installato:
1. Una GPU NVIDIA compatibile.
2. CUDA Toolkit (per utilizzo il locale)
3. Compilatore C++ che supporti CUDA (come ad esempio `nvcc` installato dal CUDA Toolkit)

Se non si dispone di una GPU NVIDIA è possibile compilare ed eseguire il progetto [kmeansCUDA.ipynb](kmeansCUDA.ipynb) senza modifche utilizzando la GPU NVIDIA Tesla T4 fornita da Google Colab.

## Setup e Utilizzo (Windows)
### 1. Clonare la repository
```bash
git clone Elia29/Kmeans_CUDA
cd Kmeans_CUDA
```
### 3. Eseguire il programma
```bash
[kmeansCUDA.cpp](kmeansCUDA.cpp)
```

> [!NOTE]
> Al termine dell'esecuzione, Il programma crea automaticamente tre diversi file:
> - `table_points_threads.csv`: Lo speedup calcolato su dataset di dimensioni crescenti
> - `table_dims_threads.csv`: Lo speedup per dimensioni crescenti
> - `table_clusters_threads.csv`: Lo speedup variando il numero di cluster

## Fonti
Il dettaglio teorico dell'algoritmo e i risultati dei test di performance sono consultabili qui:
**[Leggi l'articolo (PDF)](kmeansCUDA.pdf)**

## Licenza
Questo progetto è distribuito sotto la licenza [MIT](LICENSE).
