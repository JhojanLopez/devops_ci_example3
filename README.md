# Descripción

Este proyecto es usado como ejemplo de ci donde el proceso sea completamente automatizado (notificaciones,ejecucion automatica, pruebas automaticas), donde una vez
se valide la integracion correctamente se haga el merge en el repositorio remoto eliminando la subrama distinta a la main.

## Configuracion de pipeline
1. Configurar el pipeline de tal modo que no sea automatico (sin disparadores)
2. Agregar el sgte apartado en el pipeline ya que jenkins hara un push en el repositorio remoto y debe autenticarse como cliente:

![config1.png](assets/config1.png)

3. Agregar en build steps los sgtes comandos para que haga merge a la rama principal(se debe tener en cuenta que el pipeline descargara cambios de la rama feature/addtest):
```shell
git branch
git checkout main
git merge origin/feature/addtest
```

![config1.png](assets/config2.png)

4. Agregar ejecuciones finales en la seccion Acciones para ejecutar después., para que se pushee el cambio del merge una vez el build con las pruebas fue ejecutada correctamente

![config3.png](assets/config3.png)