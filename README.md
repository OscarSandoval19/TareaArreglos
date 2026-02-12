# TareaArreglos
# CÓDIGO DECOMPILADO

# ¿Que clases existen?

-App.class

-BubbleSort.class

-MergeSortDemo.class

-QuickSort.class

-SumArray.class


# Qué operaciones se realizan sobre los arreglos
# 1. Creación de arreglos 
(App.class)

-iconst_4

-newarray int

Se crea un arreglo de enteros de tamaño 4 y luego se le asignan valores manualmente:

dup

iconst_0

iconst_3

iastore

Es equivalente a:
int[] arr = {3, 5, 2, 9};

# 2. Acceso a elementos
Se utiliza:
iaload

Es equivalente a:
arr[i]

# 3. Asignación de valores
Se utiliza:
iastore

Es equivalente a:
arr[i] = valor;

# 4. Iteración (Recorrido de arreglos)
(SumArray)

Se utiliza:

iload 5

iload 4

if_icmpge 35

Se observa un ciclo for que es equivalente a:

for (int i = 0; i < arr.length; i++) {

    suma += arr[i];
    
}

# 5. Suma de elementos
(SumArray)

Se utiliza:
iadd

Se van acumulando los valores del arreglo.

Es equivalente a:
total += arr[i];

# 6. Copia de arreglos
(MergeSortDemo)

Se utiliza:
Arrays.copyOfRange

Indica que el arreglo se divide en subarreglos.

Es equivalente a:

int[] left = Arrays.copyOfRange(arr, 0, mid);

int[] right = Arrays.copyOfRange(arr, mid, arr.length);


# Qué algoritmos de ordenamiento se utilizan
Se implementan 3 algoritmos:

# 1. Bubble Sort
# Clase: BubbleSort

# FRAGMENTO RELEVANTE:

# if_icmple

Es una comparación entre elementos consecutivos y un posible intercambio.

Es equivalente a:

if (arr[j] > arr[j + 1]) {

    int temp = arr[j];
    
    arr[j] = arr[j + 1];
    
    arr[j + 1] = temp;
    
}

# 2. Quick Sort

# Clase: QuickSort

# FRAGMENTO RELEVANTE:

# invokespecial partition

# invokevirtual quickSort

Indica el uso de método partition y llamadas recursivas

Es equivalente a:

int pivotIndex = partition(arr, low, high);

quickSort(arr, low, pivotIndex - 1);

quickSort(arr, pivotIndex + 1, high);

# 3. Merge Sort

# Clase: MergeSortDemo

# FRAGMENTO RELEVANTE:

# Arrays.copyOfRange

Indica una división del arreglo en dos partes.

Es equivalente a:

mergeSort(left);

mergeSort(right);

merge(left, right, arr);

# Parte 2: Ejercicio Algorítmico

Mientras se recorre el arreglo una sola vez, se mantienen actualizadas cuatro variables:

- mayor

- segundoMayor

- menor

- segundoMenor

Cada vez que se lee un nuevo número, verifico si modifica alguna de las 4 variables.

Algoritmo Parte2

Entrada: arreglo A de tamaño n

Si n < 2 entonces

    Mostrar "No hay suficientes elementos"
    
    Terminar

 // Inicialización

Si A[0] > A[1] entonces

    mayor ← A[0]
    
    segundoMayor ← A[1]
    
    menor ← A[1]
    
    segundoMenor ← A[0]
    
Sino

    mayor ← A[1]
    
    segundoMayor ← A[0]
    
    menor ← A[0]
    
    segundoMenor ← A[1]
    
FinSi

// Se recorre el arreglo desde la posición 2

Para i desde 2 hasta n-1 hacer

// Se actualiza mayor y segundoMayor


    Si A[i] > mayor entonces
    
        segundoMayor ← mayor
        
        mayor ← A[i]
        
    Sino si A[i] > segundoMayor y A[i] ≠ mayor entonces
    
        segundoMayor ← A[i]
        
    FinSi

    // Se actualiza menor y segundoMenor
    
    Si A[i] < menor entonces
    
        segundoMenor ← menor
        
        menor ← A[i]
        
    Sino si A[i] < segundoMenor y A[i] ≠ menor entonces
    
        segundoMenor ← A[i]
        
    FinSi

FinPara

Mostrar segundoMayor

Mostrar segundoMenor

FinAlgoritmo

# Explicacion: ¿Porque el algoritmo funciona?

El algoritmo funciona porque mantiene siempre actualizados los valores extremos:

- mayor contiene el valor más grande visto hasta el momento.

- segundoMayor contiene el segundo más grande.

- menor contiene el más pequeño.

- segundoMenor contiene el segundo más pequeño.

En cada iteración se compara el elemento actual con los valores extremos.

- Si es mayor que el máximo actual, manda el máximo anterior a segundo máximo.

- Si es menor que el mínimo actual, manda el mínimo anterior a segundo mínimo.

No es necesario ordenarlo porque solo se compara contra los valores relevantes y solo se recorre el algoritmo una vez, lo cual cumple con la restriccion impuesta.

# Codigo resultante:

Algoritmo Parte2

Entrada: arreglo A de tamaño n

Si n < 2 entonces

    Mostrar "No hay suficientes elementos"
    
    Terminar
    
Si A[0] > A[1] entonces

    mayor ← A[0]
    
    segundoMayor ← A[1]
    
    menor ← A[1]
    
    segundoMenor ← A[0]
    
Sino

    mayor ← A[1]
    
    segundoMayor ← A[0]
    
    menor ← A[0]
    
    segundoMenor ← A[1]
    
FinSi

Para i desde 2 hasta n-1 hacer

    Si A[i] > mayor entonces
    
        segundoMayor ← mayor
        
        mayor ← A[i]
        
    Sino si A[i] > segundoMayor y A[i] ≠ mayor entonces
    
        segundoMayor ← A[i]
        
    FinSi

    Si A[i] < menor entonces
    
        segundoMenor ← menor
        
        menor ← A[i]
        
    Sino si A[i] < segundoMenor y A[i] ≠ menor entonces
    
        segundoMenor ← A[i]
        
    FinSi

FinPara

Mostrar segundoMayor

Mostrar segundoMenor

FinAlgoritmo
