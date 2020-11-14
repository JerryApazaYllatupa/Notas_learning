## Tmux (Multiplecsor de terminal)



Una herramienta que te permite dividir una pantalla de terminal en varias ventanas, Esta herramienta es ideal para acelerar muchas tareas



Instalación

```bash
sudo apt-get install tmux
```

Iniciar tmux

```bash
tmux 
# con este comando activamos la terminal en un entorno de tmux e iniciamos tmux
```

tmux se basa en sesiones, podemos tener o abrir múltiples sesiones en  una sola  terminal y en cada sesión tener múltiples ventanas de terminal

### Para finalizar una session

```bash
exit
```

### Terminar con todas las sesiones

```bash
tmux kill-server
```

## Comandos para controlar tmux

Tmux trabaja con comandos para realizar tareas especificas y para realizar estas tareas, tenemos primero que ejecutar estas combinaciones de tecla `CRTL + B`, osea presionamos estas teclas y saltamos, para luego presionar el siguiente tecla para ejecutar tareas especificas

- Abrir nueva sesión

  ```bash
  CTRL+B, C
  ```

- Moverte de una sesión a otra, tmux guarda las sesiones por números iniciando en 0 a más 

  ```
  CTRL+B, 0
  CTRL+B, 1
  ```

- Listar las sesiones

  ```bash
  CTRL+B, w
  ```

- Renombrar sesiones

  ```bash
  CTRL+B ,
  # control b mas ,
  # en parte inferior nos aprecera una opcion de amarillo para llenar el nombre
  ```

- Terminal las sesiones

  ```
  CTRL+B, 
  ```

  



## Dividir pantallas 

- Dividir una pantalla hacia abajo

  ```bash
  CTRL+B,  ""
  ```

- dividir hacia la derecha

  ```bash
  CTRL+B, %
  ```

- Moverte entre las ventanas 

  ```
  CTRL+B, y direccionales arriba abajo derecha izquierda
  
  ```

- Redimensionar las pantallas divididas

  ```bash
  CTRL+B, y direccionales arriba abajo derecha izquierda per sin soltar las primeras teclas
  ```

   