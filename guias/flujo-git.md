# Flujo de trabajo: fork → rama → commit → Pull Request

Esto ya lo practicamos en la semana 1. Aquí está completo para que no dependan de la memoria.

## 1. Fork (solo un integrante)

1. Entra al repositorio del curso y da clic en **Fork** (esquina superior derecha).
2. Deja el nombre como está y crea el fork en **tu cuenta personal**.
3. En tu fork: **Settings → Collaborators → Add people** y agrega a tus dos compañeros por su usuario de GitHub. Ellos tienen que aceptar la invitación (les llega por correo o en github.com/notifications).

## 2. Abrir el entorno (los tres)

Cada integrante abre **el fork del equipo**, no el repositorio original:

- **Codespaces:** botón verde **Code → Codespaces → Create codespace on main**.
- **O en local:**
  ```bash
  git clone https://github.com/USUARIO-DEL-FORK/aecbd-lab-s06-esquema-relacional.git
  cd aecbd-lab-s06-esquema-relacional
  ```

Configuración que les recomiendo antes de empezar:
```bash
git config pull.rebase false
```

## 3. Rama y carpeta del equipo (solo quien hizo el fork)

Usen su número de equipo **con dos dígitos** (`equipo-02`, `equipo-07`, …):

```bash
git switch -c equipo-02
cp -r equipos/_plantilla equipos/equipo-02
git add equipos/equipo-02
git commit -m "Equipo 02: carpeta de trabajo creada desde la plantilla"
git push -u origin equipo-02
```

Los otros dos integrantes traen esa rama:
```bash
git fetch origin
git switch equipo-02
```

## 4. Trabajar sin pisarse

- Antes de empezar a editar: `git pull`
- Al terminar un cambio pequeño:
  ```bash
  git add equipos/equipo-02
  git commit -m "Equipo 02: mapeo de la relación N:M inscripción"
  git push
  ```
- Mensajes de commit que digan **qué** cambió. `"cambios"` o `"avance"` no le dicen nada a nadie, incluido tú dentro de dos semanas.
- Si les sale un conflicto: no entren en pánico, levanten la mano.

Una sugerencia para repartirse el trabajo sin conflictos: mientras uno escribe en `gimnasio.md`, otro escribe en `esquema-relacional.md`, y el tercero revisa lo que van subiendo. Roten.

## 5. Pull Request (a las 11:30, aunque no esté terminado)

1. En su fork, GitHub les va a mostrar el aviso **Compare & pull request**. Si no aparece: pestaña **Pull requests → New pull request**.
2. Verifiquen la dirección:
   - **base repository:** el repositorio del curso · **base:** `main`
   - **head repository:** su fork · **compare:** `equipo-02`
3. Título: `Equipo 02 — Esquema relacional (Gestión de viajes)` (con su número y dominio).
4. Llenen la plantilla que aparece en la descripción.
5. **Create pull request.**

A partir de ese momento, cada `git push` que hagan a su rama actualiza el Pull Request automáticamente. No abran otro.
