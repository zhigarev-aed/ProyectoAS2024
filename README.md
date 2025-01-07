Trabajo : Eliminación de ruido sintético en imágenes
Grupo E: Alejandra Venegas, Rebeca Company, Marta Medina, Alejandro Cornelio y Ilia Zhigarev.

Elementos en github:

- memoria.Rmd: código principal del trabajo. Actualmente esta configurado para que su knit en R genere exactamente el archivo memoria.pdf sin necesidad de ejecutar el código completo debido al tiempo de ejecución.
- memoria.pdf: archivo pdf generado a partir de memoria.Rmd. Explicación y desarrollo del trabajo.
- Carpeta fotos: imágenes tomadas con una cámara a emplear en el proyecto. 5 fotografías: 4 de gran calidad y 1 de menor.
- Carpeta imwd: imágenes resultado de la eliminación de ruido con transformadas wavelets empleando el algoritmo de Mallat.
- Carpeta denoisedwt2d: imágenes resultado de la eliminación de ruido empleando la función denoise.dwt.2d del paquete waveslim de R.
- Carpeta fftsfit: imágenes resultado de la eliminación de ruido empleando tranformadas de Fourier.

Resumen del trabajo y funciones de programación empleadas:

En este trabajo se explora la capacidad de los wavelets para la eliminación de ruido en imágenes. Para ello,
se genera diferentes tipos de ruido sintético (funciones NOISETYOPES y add_noise_to_image) y se determinan los parámetros más eficaces de los wavelets
para su eliminación a través de 3 métodos distintos.

 - Método 1: Transformada wavelet (función imwd), imposición de un umbral a los coeficientes (función threshold) y transformada inversa (funcion imwr).
 - Método 2: Proceso anterior completo y directo con función denoise.dwt.2d
 - Método 3: Desplazamiento de los ejes (fftshift), transformada de Fourier (fft), vuelta a ejes originales (ifftshift) y transformada inversa. Este último método no emplea wavelets.

