# Refactorización y Validación

## Refactorización

```java
package ED.desarrollo;
import java.util.ArrayList;
import java.util.Collection;
 
public class CostPersonal {
 
	static float CostDelPersonal(Trabajador trabajadores[]) {
		 float costeFinal = 0;
		 Trabajador trabajador;
		 for (int i = 0; y < trabajadores.length; i++) {
			 trabajador = trabajadores[i];
			 if ( trabajador.getTipusTrabajador() == Trabajador.DIRECTOR|| trabajador.getTipusTrabajador() == Trabajador.SUBDIRECTOR) {
				 costeFinal += trabajador.getNomina();
			 }
			 else
			 {
				 costeFinal += trabajador.getNomina() + (trabajador.getHorasExtras() * 20);
			 }
		 }
		 return costeFinal;
	}	
}

```
### En la refactorización:

* Cambio el nombre del método de CostDelPersonal a calcularCostePersonal para seguir las convenciones de nomenclatura de Java y hacerlo más descriptivo.
* Modifico el bucle for para utilizar el bucle for-each, lo que hace que el código sea más claro y menos propenso a errores.
* Elimino la declaración de la variable trabajador y la asignación dentro del bucle for ya que se puede acceder directamente al elemento del array trabajadores[i].
* Utilizo el operador += para simplificar la suma del coste final.

```java
package ED.desarrollo;

public class CostPersonal {

    public static float calcularCostePersonal(Trabajador[] trabajadores) {
        float costeFinal = 0;
        
        for (Trabajador trabajador : trabajadores) {
            if (trabajador.getTipusTrabajador() == Trabajador.DIRECTOR || trabajador.getTipusTrabajador() == Trabajador.SUBDIRECTOR) {
                costeFinal += trabajador.getNomina();
            } else {
                costeFinal += trabajador.getNomina() + (trabajador.getHorasExtras() * 20);
            }
        }
        
        return costeFinal;
    }   
} ``` 

