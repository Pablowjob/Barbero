# Barbero

Descripción del problema:
Una peluquería en la que hay un barbero, una silla de peluquero y N sillas para que se sienten los clientes en espera, si e que los hay.
Si no hay clientes presentes, el barbero se sienta en su silla de peluquero y se duerme.
Cuando llega un cliente, éste debe despertar al barbero dormilón
Si llegan más clientes mientras el barbero corta el cabello a un cliente, se sientan (si hay sillas desocupadas) o salen de la barbería (si todas las sillas están ocupadas).

Especificaciones para su implementación:
El programa deberá estar escrito en ANSI C y utilizar hilos POSIX y variables MUTEX.
el barbero debrá tardar en cortar el pelo o la barba al cliente en un tiempo aleatorio de 1, 2 o 3 segundos (usar la función sleep).
Llegará un cliente nuevo cada 1 o 2 seg. (aleatorio). Sólo habrá 20 clientes.
Sólo hay 4 sillas de espera.
Se deberá reportar cuando:
  a) El barbero está cortando el cabello o barba del cliente, por x segundos.
  b) Un cliente se espera y ocupa la silla "n".
  c) Un cliente se va porque no hay sillas disponibles.
 
Estructura del programa:
La función principal creará dos hilos secundarios:
El hilo del barbero y el hilo que creará hilos cliente.
El hilo que creará hilos cliente tendrá el siguiente aspecto:

  crea_clientes(){
    int i;
    tipo_hilo cliente[20];
    for(i=0;i<20;i++)
    {
      sleep(x);
      crea_hilo(cliente[i]);
    }
    for(i=0;i<20;i++)
    {
      join_hilo(cliente[i]);
    }
    exit_hilo(NULL);
   }
   
El programa terminará cuando terminen los 20 hilos cliente (ya sea que fueron atendidos o que sefueron porque no había sillas disponibles).

FECHA LÍMITE 11 DE OCTUBRE DE 2018


