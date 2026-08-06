Instalador del Asistente FDA para Windows.

## Cómo se instala

1. Descarga el `.exe` de aquí abajo y ejecútalo.
2. Windows puede avisar que no reconoce el programa: elige "Más información"
   y luego "Ejecutar de todas formas".
3. Sigue el asistente de instalación hasta el final.
4. Ábrelo. La primera vez te pedirá un nombre para esta computadora.
5. Queda esperando a que un administrador la active. En cuanto la active, la
   pantalla se quita sola y podrás empezar a trabajar.

No hace falta ser administrador de la computadora: el asistente se instala
dentro del perfil del usuario que lo corre.

## Si ya tenías el asistente instalado

Corre este instalador encima: cierra el asistente solo, conserva tus llaves y
tu historial, y actualiza el programa.

## Comprobar que el archivo es el correcto (opcional)

El archivo `.sha256` trae la huella del instalador. En PowerShell:

    Get-FileHash -Algorithm SHA256 .\NOMBRE_EXE
