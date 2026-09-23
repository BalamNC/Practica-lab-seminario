# Revisión cruzada entre equipos

De 11:30 a 11:48 cada equipo revisa el Pull Request de otro equipo. La revisión se hace **en GitHub**, con comentarios sobre las líneas del archivo, igual que se hace en cualquier equipo de desarrollo.

## Quién revisa a quién

| Equipo que revisa | Revisa el PR del |
|---|---|
| Equipo 02 | Equipo 03 |
| Equipo 03 | Equipo 04 |
| Equipo 04 | Equipo 05 |
| Equipo 05 | Equipo 06 |
| Equipo 06 | Equipo 07 |
| Equipo 07 | Equipo 08 |
| Equipo 08 | Equipo 02 |

Si el equipo que les toca todavía no abrió su PR, avísenme y los reasigno.

## Cómo comentar en el Pull Request

1. Abran el PR del otro equipo → pestaña **Files changed**.
2. Pasen el cursor sobre la línea que quieren comentar y den clic en el **+** azul.
3. Escriban el comentario y den **Start a review** (no "Add single comment", para que todos sus comentarios lleguen juntos).
4. Al terminar: **Review changes → Comment → Submit review**.

## Qué preguntar

No están calificando al otro equipo. Están haciendo las preguntas que mañana les haría PostgreSQL al ejecutar el DDL, o que les haría yo en la defensa. Usen estas como guía:

**Llaves primarias**
- ¿Cada tabla tiene llave primaria? ¿Es realmente única en el negocio, o solo en los datos de ejemplo que imaginaron?
- Si usaron un `id` artificial, ¿hay algún otro atributo que también debería ser `UNIQUE`?

**Llaves foráneas y cardinalidad**
- En cada relación 1:N, ¿la llave foránea quedó del lado de la N?
- ¿Las llaves foráneas obligatorias y las opcionales (`?`) coinciden con la participación que dibujaron en el E/R?
- En las relaciones 1:1, ¿de qué lado pusieron la llave foránea y por qué? ¿Le pusieron `UNIQUE`?

**Relaciones N:M**
- ¿Toda N:M del E/R se convirtió en una tabla intermedia?
- ¿Qué incluye la llave primaria de esa tabla? ¿El negocio permite que la misma pareja se repita (una segunda compra, una segunda cita, un segundo préstamo del mismo libro)? Si sí, ¿la llave lo permite?
- Los atributos de la relación, ¿quedaron en la tabla intermedia y no en alguna de las entidades?

**Casos especiales**
- Atributos multivaluados (varios teléfonos, varios correos): ¿se fueron a su propia tabla?
- Entidades débiles: ¿su llave primaria incluye la llave de la entidad de la que dependen?
- Relaciones recursivas (un empleado que supervisa a otro): ¿la llave foránea apunta a la misma tabla y admite `NULL` donde debe?

## Un buen comentario frente a uno que no sirve

| No sirve | Sí sirve |
|---|---|
| "Está mal la tabla de reservaciones." | "En `RESERVACION` la llave es (`id_cliente`, `id_funcion`). Si un cliente compra boletos dos veces para la misma función, la segunda compra no se puede registrar. ¿Es eso lo que quieren?" |
| "Falta una FK." | "En el E/R `PLATILLO` pertenece a una `CATEGORIA`, pero no veo `id_categoria` en `PLATILLO`." |
| "Se ve bien 👍" | "Revisamos las 4 relaciones 1:N y las FK están del lado correcto. La única duda es si `telefono` en `PROVEEDOR` puede tener más de un valor." |

## Después de recibir comentarios

El equipo autor responde **cada** comentario en el PR: lo corrige y hace push, o explica por qué no lo corrige. Las dos respuestas son válidas; lo que no es válido es ignorarlo. En el documento de Google registran los tres comentarios más importantes que recibieron y qué hicieron con cada uno.
