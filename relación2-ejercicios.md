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

~~~
@describe('TripManager tests')
def _():

    #Testea la funcion checkCity de la clase TripManager
    @it('Revisado que una ciudad existe.')
    def testCheckCity():
        tripManager = TripManager.TripManager()
        assert(True, tripManager.checkCity("Granada"))
        assert(False, tripManager.checkCity("Grandadada"))

    #Testea la funcion setTrips de la clase TripManager
    @it('Revisado que se introduce un origen y un destino válidos para el viaje.')
    def testSetTrips():
        tripManager = TripManager.TripManager()
        assert (1, tripManager.setTrips("",""))
        assert (2, tripManager.setTrips("Grandadada",""))
        assert (3, tripManager.setTrips("Granada","Grandadada"))
        assert (0, tripManager.setTrips("Granada","Madrid"))

    #Testea la funcion getTrips de la clase TripManager
    @it('Revisado que solo se devuelven viajes si hay viajes guardados.')
    def testGetTrips():
        tripManager = TripManager.TripManager()
        tripManager.trips = None
        assert (1, tripManager.getTrips())

        tripManager.setTrips("Granada","Madrid")
        api = BlaBlaCarApi(api_key="713d0cd3340f4e428c54177955de9f25", locale="es_ES", currency="es_ES")
        tipo = type(api.trips(frm="Granada", to="Madrid")).__name__
        tipo2 = type(tripManager.getTrips()).__name__
        assert (tipo, tipo2)
~~~
