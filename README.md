# lists

Listas que Lean Browser descarga en runtime. Por ahora hay una sola.

## sso_hosts.txt

Dominios de login que el navegador no debe enrutar entre contextos. Si un login se rompe porque la pestaña salta de contexto a mitad del flujo, se agrega el dominio aca y listo, no hace falta sacar una build nueva.

El formato es simple. La primera linea tiene que ser `# lean-sso` y despues va un dominio por linea. Si empieza con punto cubre todos los subdominios

```
# lean-sso
login.miproveedor.com
.miproveedor.com
```

Ojo que los sufijos muy amplios tipo `.com` el navegador los ignora, tiene que ser al menos un dominio real. Tampoco van esquemas ni puertos ni rutas, solo el dominio pelado.

Para que un cambio llegue a los navegadores hay que publicar un release nuevo (v1.0.1, v1.0.2 y asi). La descarga va por jsDelivr con `@latest` y eso se resuelve mirando los tags del repo, sin tag nuevo el cambio no sale de aca.

La lista solo suma excepciones sobre las que el navegador ya trae compiladas. Una lista rota, vacia o caida no rompe nada, en el peor caso un dominio nuevo queda sin eximir hasta el proximo tag.

Si un login te falla en Lean y crees que falta un dominio aca, abre un issue con el dominio y que proveedor es.
