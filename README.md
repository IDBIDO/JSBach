# El doble interprete de JSBach.
Interprete para el lenguaje de programacion musical JSBach. La salida del interprete es un pdf con la partitura y unos ficheros de sonido que reproduce dicha partitura.

## Instalacion

ANTLR:
```bash
pip install antlr4-python3-runtime==4.7.1
antlr4 -Dlanguage=Python3 -no-listener -visitor jsbach.g4
```
LilyPond: https://lilypond.org
Para las pruebas se ha usado la version 2.22.0. No se ha incluido la instruccion " \version "2.XX.X" " en el fichero de salida .lily. Asi que tambien funcionara para versiones mas recientes.

Timidity:
```bash
 sudo apt-get install -y timidity  
```

FFmpeg:
```bash
sudo apt install ffmpeg
```

##Usage
Ejecucion:
1. Empezando por la funcion por defecto Main:
```bash
python3 jsbach.py input.jsb
```
2. Empezando por otra funcion diferente de Main:
```bash
python3 jsbach.py input.jsb Nombre_Funcion
```

##Detalles
Si el programa no hace uso de la instruccion de reproduccion "<:>" puede pasar que los ficheros de salida no se puedan reproducir.

Al compilar un programa saldra muchos mensages. Estos pueden ser avisos de Lilypond, ffmpeg y timidity. Los outputs de texto generados por la instruccion <!> estan al principio de todo.

Al recompilar un programa te puede preguntar sobre si quieres Rescribir el archivo de salida. Para que la salida sea correcta dile que si.
