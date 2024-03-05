# Refactorización y Validación

## Refactorización

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
}
```
*** En la refactorización:***

* Cambié el nombre del método de CostDelPersonal a calcularCostePersonal para seguir las convenciones de nomenclatura de Java y hacerlo más descriptivo.
* Modifiqué el bucle for para utilizar el bucle for-each, lo que hace que el código sea más claro y menos propenso a errores.
* Eliminé la declaración de la variable trabajador y la asignación dentro del bucle for ya que se puede acceder directamente al elemento del array trabajadores[i].
* Utilicé el operador += para simplificar la suma del coste final.

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

