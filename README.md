Estad�stica divertiva y running backs de la NFL
--------------------------------------------------

#Traducciones:
* [Espa�ol](README.md)
* [Ingles](README-en.md)

## La idea y el art�culo.
Para la temporada 2013 solo 2 jugadores de los mejores 10 med�an mas de 6 pies: Adrian Peterson y Arian Foster. 
La NFL se caracteriza por tener a los jugadores mas grandes pero no necesariamente para la posici�n de corredor. 
Primero: No queremos a un jugador demasiado alto ya que le podr�n ver muy f�cil por atras de la l�nea. Los corredores mas 
peque�os se pueden esconder atras de los jugadores grandes, "la l�nea". Tambi�n queremos que tengan un centro de gravedad bajo.

�Ha cambiado en algo la NFL desde que empez�? S� y mucho. Pero, �c�mo se han generado estos cambios? Aprendiendo del pasado.
La idea de analizar la base de datos de todos los corredores proviene de un art�culo escrit� por `bleacherreport.com`.
�Acaso la NFL a aprendido del pasado? �Tenemos a los mejores corredores posibles? BJKissel hace un intento en dise�ar al mejor 
corredor posible, basandose en la altura, el peso y la velocidad. Toma como referencia los corredores de la temporada 2013.
Pero, �Qu� nos dice la historia?

<br/>
<p align="center">
<img src="Images/corredores_tiempo.gif" alt="gif">
</p><br/>
## Altura promedio por decadas.
* 1920 - 1930 es: `178.25453749999988`
* 1930 - 1940 es: `181.2450224215246`
* 1940 - 1950 es: `181.38997468354438`
* 1950 - 1960 es: `182.5032027027025`
* 1960 - 1970 es: `184.5428217821781`
* 1970 - 1980 es: `183.91626603325398`
* 1980 - 1990 es: `181.4760692307693`
* 1990 - 2000 es: `181.45665420560732`
* 2000 - 2010 es: `181.72643386243396`
* 2010 - 2016 es: `180.91711004784682`
* 2017 es: `180.15961904761895`
Esta imagen muestra como ha cambiado la altura y el peso a trav�s de las decadas desde 1920 hasta la temporada del 2017. 
Durante los cicuentas y hasta finales de los setentas la distribuci�n de la altura se encontrar� a la derecha y en las decadas 
posteriores retroceder� a una media de 181cm. 
En el eje horizontal o de las abscisas se muestra la altura y el eje vertical o real se muestra el peso. Por lo que un aumento
en la altura desplazar�a las observaciones a la derecha y un aumento en el peso hacia arriba. Parece que los corredores son mas 
fuertes hoy en dia y menos altos que en decadas anteriores a los ochentas.
Para entender mejor el aprendizaje sobre los corredores graficaremos boxplots (diagrama de caja y bigotes) que son dificiles de entender
por lo que explicar� un boxplot con un ejemplo de la temporada 2017.

## Entendiendo estad�sticas con la informaci�n de la temporada 2017. 
El boxplot es de las herramientas mas completas para hacer un an�lisis preliminar sobre los datos obtenidos. Ya que a diferencia del 
histograma permite de forma mas sencilla comparar dos distribuciones. Comunmente queremos saber que tan normal parecen los datos, 
�usa un boxplot!
La normalidad es m�s f�cil de ver graficamente con un histograma (pero no te preocupes, tambi�n con un boxplot). 
Primero graficaremos la estatura de los corredores activos de  la temporada 2017 y la compararemos con una distribuci�n normal.  
<br/>
<p align="center">
<img src="Images/histograma_normal.png" alt="histograma">
</p><br/>
La altura minima es 167.5cm. Son dos jugadores con esa altura:
* `Tarik Cohen`: 377 yardas
* `Jacquizz Rodgers`: 244 yardas
La altura maxima es de 192cm. Son tres jugadores con esa estatura:
* `Derrick Henry`: 744 yardas
* `Latavius Murray`: 842 yardas
* `Rod Smith`: 232 yardas
La media es de 180.16cm, pero en el histograma claramente podemos ver que la moda se encuentra en otro intervalo.
Por lo que es mas comun ver corredores mas peque�os que la media. 
Sin embrago, �parece normal, cierto? Bueno, no los podemos comparar con la simple vista. Podemos usar un Q-Q plot. Que compara los valores 
vistos con valores de probabilidad hipoteticos normales, una distribuci�n normal ser� una linea de 45 grados. En este caso no parece normal.
<br/>
<p align="center">
<img src="Images/Q-Q_plot.png" alt="Q-Q plot">
</p><br/>
Como podemos ver los puntos parecen encontrarse en ciertas regiones, esto se debe a que no hay continuidad en la altura.
Por lo que el Q-Q plot no es un buen indicador. 
Una de las suposiciones de normalidad es una media igual, una mediana igual y una moda igual. La media es �180.2104�
La mediana es �180.15961904761895� y no hay moda (o todos los valores son la moda). 
�Hagamos estadisticas mas avanzadas!
Para probar la normalidad de una distribuci�n podemos usar la prueba X^2 de normalidad, la prueba Kolmogorov-Smirnov, 
la prueba Shapiro-Wilk y la prueba Lilliefors estas ultimas son la mas famosa para normalidad. Todas son una especie de 
pruebas de hipotesis, donde tenemos una hipotesis nula y una alternativa. 

* El valor de la prueba Kolmogorov-Smirnov es: `0.123436625014`
* El valor p de la prueba es: `5.73947997152e-10`
* El valor de la prueba Shapiro-Wilk es: `0.9677223563194275`
* El valor p de la prueba es: `1.819115823309403e-05`

La prueba Shapiro Wilk plantea la hipotesis nula que las observaciones provienen de una distribuci�n normal.
Ahora veamos una distribuci�n acumulada de la estatura de los corredores y su normal:
<br/>
<p align="center">
<img src="Images/Histograma_acumulado.png" alt="Kolmogorov">
</p><br/>
Los datos y la imagen niegan la normalidad de nuestra distribuci�n. Tanto la prueba Lilliefors como la prueba Kolmogorov-Smirnov
se basan en la distancia mas extrema de la distribuci�n acumulada vista y la distribucion acumulada hipotestica normal.
Adem�s las 2 pruebas que realizamos tienen valores p extremadamente peque�os. 
Y se puede ver muy "claro" en el boxplot (la normalidad) gracias a la dispersi�n de las cajas. Nos muestra valores extremos tambien.
Para este caso son los jugadores con mas de 800 yardas en la temporada 2017.
<br/>
<p align="center">
<img src="Images/entender_boxplot.png" alt="boxplot">
</p><br/>

```
| Nombre               | Altura  | Peso | Yardas | Status | Posicion | 
|----------------------|---------|------|--------|--------|----------| 
| "Ajayi, Jay"         | 182.88  | 223  | 873.0  | ACT    | RB       | 
| "Anderson, C.J."     | 172.5   | 224  | 1007.0 | ACT    | RB       | 
| "Bell, Le'Veon"      | 185.928 | 225  | 1291.0 | ACT    | RB       | 
| "Collins, Alex"      | 177.5   | 210  | 973.0  | ACT    | RB       | 
| "Crowell, Isaiah"    | 180.0   | 225  | 853.0  | ACT    | RB       | 
| "Elliott, Ezekiel"   | 182.88  | 228  | 983.0  | ACT    | RB       | 
| "Fournette, Leonard" | 182.88  | 228  | 1040.0 | ACT    | RB       | 
| "Freeman, Devonta"   | 172.5   | 206  | 865.0  | ACT    | RB       | 
| "Gordon, Melvin"     | 185.928 | 215  | 1105.0 | ACT    | RB       | 
| "Gore, Frank"        | 175.0   | 212  | 961.0  | ACT    | RB       | 
| "Gurley, Todd"       | 185.928 | 227  | 1305.0 | ACT    | RB       | 
| "Howard, Jordan"     | 182.88  | 224  | 1122.0 | ACT    | RB       | 
| "Hunt, Kareem"       | 177.5   | 216  | 1327.0 | ACT    | RB       | 
| "Hyde, Carlos"       | 182.88  | 235  | 938.0  | ACT    | RB       | 
| "Ingram, Mark"       | 175.0   | 215  | 1124.0 | ACT    | RB       | 
| "Lewis, Dion"        | 172.5   | 195  | 896.0  | ACT    | RB       | 
| "Lynch, Marshawn"    | 180.0   | 215  | 891.0  | ACT    | RB       | 
| "McCoy, LeSean"      | 180.0   | 210  | 1138.0 | ACT    | RB       | 
| "Miller, Lamar"      | 177.5   | 225  | 888.0  | ACT    | RB       | 
| "Murray, Latavius"   | 192.024 | 230  | 842.0  | ACT    | RB       | 
```

## Aprendizaje.
>El aprendizaje es una propiedad de la actividad mental que produce en el organismo el resultado de cambiar o modificar 
>su sistema  cognitivo y su comportamiento observable. Son cambios relativamente permanentes que ocurren por condiciones de pr�tica.

�Listo! Ahora si podemos entender como ha cambiado la estatura de los corredores a traves de las decadas y sobre todo el 
aprendizaje (prueba y error) para dise�ar al mejor running back de la NFL. 
<br/>
<p align="center">
<img src="Images/boxplot_historico.png" alt="historico">
</p><br/>
�Qu� vemos?
En los a�os veinte la mediana es muy baja pero hay muchos outliers (por lo que tal vez se ten�a que la idea era tener corredores altos)
y la medida de tendencia central es tan baja por la estatura media de los americanos. 
De los a�os treintas a los a�os setentas la mediana de la estatura claramente se eleva. Estos a�os sirven de aprendizaje.
A partir de la decada de los ochentas vemos que la mediana se ha reducido y se ha establecido hasta la temporada 2017. 
Adem�s las distribuciones se han encogido, lo que nos muestra que la NFL ahora sabe lo que quiere.
Esta es informaci�n poblacional, por lo que sea lo que sea que veamos en este grafico es la realidad (a diferencia de 
usar una muestra). Sin embargo, realizaremos una prueba de hipotesis de la diferencia de dos muestras independientes.
(Para mayor informaci�n correr el codigo).

<br/>
<p align="center">
<img src="Images/prueba_hipotesis.png" alt="hipotesis">
</p><br/>
Podemos ver claramente que es improbable que se haya dado por aleatoriedad la altura de los corredores. 
Pero, �Que no son mejores los jugadores altos, �que no los mas altos tienen mas yardas? Veamos que pasa en la temporada 2017.
Al igual que al principio usaremos un gr�fico de dispersi�n pero en este caso las observaciones estar�n en 
funci�n de las yardas por temporada. Claramente se ve que no hay una relacion entre las yardas por temporada y la altura o inclusive el peso. 

<br/>
<p align="center">
<img src="Images/dispersion.png" alt="dispersion">
</p><br/>

## �Qu� hace el codigo?
Primero, el codigo extrae (scrape) toda la informacion de los corredores historicos y del 2017 de la pagina oficial de la NFL. 
Transforma los pies en cent�metros.
Gr�fica y realiza todas las pruebas estadisticas que has visto aqu�.
Adem�s de informaci�n adicional sobre la estatura de los corredores y los full backs.

