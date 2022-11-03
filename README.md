# Evaluación #3

## General

- Implementar y evaluar un sistema de detección de intrusos usando técnicas machine learning.

### Específicos:

- Seleccionar variables, usando ganancia de información, información mutua y valores propios de matrices.
- Implementar una red neuronal artificial (ANN) usando aprendizaje híbrido (PSO+BP) para clasificar tres tipo de tráfico (normal, dos, probe).
- Evaluar el rendimiento de la ANN usando métricas de exactitud y F-scores para cada clase."

​	

# Selección de Variables:

- Datos de Training: **KDDTrain.txt**
  - Muestras: 25.192, Variables: 43
  - Variable numero 42: tipo de tráfico
    - Normal, 	Clase 1
    - DOS, 		  Clase 2
    - Probe,		Clase 3



- Datos de Testing: **KDDTest.txt**
  - Muestras: 22.544, Variables: 43
  - Clases: {1, 2, 3}



- Clase #1: Valores

  - 'normal'

    

- Clase #2: Valores

  - 'neptune', 'teardrop', 'smurf', 'pod', 'back', 'land', 'apache2', 'processtable', 'mailbomb', 'udpstorm'

    

- Clase #3: Valores

  - 'ipsweep', 'portsweep', 'nmap', 'satan', 'saint', 'mscan'



## sv.py

- Convertir Variables no-numéricas a numéricas:

  - Variables categóricas:
    - Var #2: protocolo
    - Var #3: servicio
    - Var #4: flag
    - Variables continuas
      - Vars = {1, 5:41}
  - Variable Etiqueta
    - Var #42 = {1 ó 2 ó 3}

- Normalizar cada variable = {1:41}
  $$
  x = (x-x_{min}/(x_{max}-x_{min})*(b-a) + a, a=0.01, b=0.99
  $$
  ***Usar metodo de ganancia de información***



- [ ] Crear archivo con los indices relevantes:
  - [ ] **Index.csv**: M-filas por L-columnas
- [ ] Calcular la reducción de dedundancia usando el método de descomposición de valores singulares.
  - [ ] Crear archivo con la matriz de filtro (matriz V):
    - [ ] **filter_v.csv**
- [ ] Filtrar la data usando archivo **filter_v.csv**
- [ ] Crear archivo de datos con data filtrada:
  - [ ] **dtrn.csv**: data de entrada para la red neuronal
  - [ ] **etrn.csv**: data de etiquetas para la red
- [ ] Cargar datos de testing: **KDDTest.txt**
- [ ] Convertir variables no-numéricas a numéricas
- [ ] Normalizar cada variable {1:41} usando el método previo
- [ ] Filtrar la data normalizada usando los archivos **index.csv**, **filter_v.csv**.
  - [ ] Normaliar la data filtrada
- [ ] Crear archivo con datos normalizados
  - [ ] **dtst.csv**.
- [ ] Crear etiquetas numéricas para Variable #42:
  - [ ] Caso #1: Normal
  - [ ] Caso #2: DOS
  - [ ] Caso #3: Probe
- [ ] Crear archivo de etiquetas de testing:
  - [ ] **etst.csv**

#### Configuración: selección de variables

- cnf_sv.csv

  | Numero de Muestras Train      | 1000 |
  | ----------------------------- | ---- |
  | Numero de Muestras Test       | 5000 |
  | Valor de Relevancia (0,1)     | 0.6  |
  | Numero de Vectores Singulares | 10   |
  | Clase Normal (s/n)            | 1    |
  | Clase DOS (s/n)               | 0    |
  | Clase Probe (s/n)             | 1    |

  
