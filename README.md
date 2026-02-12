# TareaArreglos
CÓDIGO DECOMPILADO

¿Que clases existen?
-App.class
-BubbleSort.class
-MergeSortDemo.class
-QuickSort.class
-SumArray.class


Qué operaciones se realizan sobre los arreglos
1. Creación de arreglos
(App.class)

iconst_4
newarray int

Se crea un arreglo de enteros de tamaño 4 y luego se le asignan valores manualmente:
dup
iconst_0
iconst_3
iastore

Es equivalente a:
int[] arr = {3, 5, 2, 9};

2. Acceso a elementos
Se utiliza:
iaload

Es equivalente a:
arr[i]

3. Asignación de valores
Se utiliza:
iastore

Es equivalente a:
arr[i] = valor;

4. Iteración (Recorrido de arreglos)
En SumArray:

Se utiliza:
iload 5
iload 4
if_icmpge 35

Se observa un ciclo for que es equivalente a:
for (int i = 0; i < arr.length; i++) {
    suma += arr[i];
}

5. Suma de elementos
En SumArray:

Se utiliza:
iadd

Se van acumulando los valores del arreglo.
Es equivalente a:
total += arr[i];

6. Copia de arreglos
En MergeSortDemo:

Se utiliza:
Arrays.copyOfRange

Indica que el arreglo se divide en subarreglos.
Es equivalente a:
int[] left = Arrays.copyOfRange(arr, 0, mid);
int[] right = Arrays.copyOfRange(arr, mid, arr.length);


Qué algoritmos de ordenamiento se utilizan
Se implementan 3 algoritmos:
1. Bubble Sort
Clase: BubbleSort

FRAGMENTO RELEVANTE:

if_icmple

Es una comparación entre elementos consecutivos y un posible intercambio.
Es equivalente a:
if (arr[j] > arr[j + 1]) {
    int temp = arr[j];
    arr[j] = arr[j + 1];
    arr[j + 1] = temp;
}

2. Quick Sort
Clase: QuickSort

FRAGMENTO RELEVANTE:

invokespecial partition
invokevirtual quickSort

Indica el uso de método partition y llamadas recursivas
Es equivalente a:
int pivotIndex = partition(arr, low, high);
quickSort(arr, low, pivotIndex - 1);
quickSort(arr, pivotIndex + 1, high);

3. Merge Sort
Clase: MergeSortDemo

FRAGMENTO RELEVANTE;

Arrays.copyOfRange

Indica una división del arreglo en dos partes.
Es equivalente a:
mergeSort(left);
mergeSort(right);
merge(left, right, arr);
