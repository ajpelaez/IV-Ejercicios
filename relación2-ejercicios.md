# Desarrollo basado en pruebas
---
## Ejercicio 1: *Hacer un pull request a este proyecto con tests adicionales, si es que faltan (en el momento que se lea este tema).*

No faltan test adicionales por añadir.

---

---

## Ejercicio 2:  *Para la aplicación que se está haciendo, escribir una serie de aserciones y probar que efectivamente no fallan. Añadir tests para una nueva funcionalidad, probar que falla y escribir el código para que no lo haga (vamos, lo que viene siendo TDD).*

Ejercicio realizado junto con el proyecto de la asignatura, aquí dejo algunas de las aserciones creadas para el test de una función:

~~~
def testCheckCity(self):
    self.tripManager = TripManager.TripManager()
    self.assertTrue(self.tripManager.checkCity("Granada"))
    self.assertFalse(self.tripManager.checkCity("Grandadada"))
~~~

---

---

## Ejercicio 3:  *Convertir los tests unitarios anteriores con assert a programas de test y ejecutarlos desde mocha, usando descripciones del test y del grupo de test de forma correcta. Si hasta ahora no has subido el código que has venido realizando a GitHub, es el momento de hacerlo, porque lo vas a necesitar un poco más adelante.*
