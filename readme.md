# ⭐ Simple Rating Widget (Vanilla JavaScript)

Este es un proyecto minimalista que implementa un componente de **calificación por estrellas (Star Rating Widget)** completamente funcional utilizando **JavaScript puro** (Vanilla JS). Es ideal para principiantes que buscan entender la manipulación básica del DOM y la gestión de eventos sin la necesidad de librerías o *frameworks* complejos.



## ✨ Características

* **Interactividad con el Mouse:** Las estrellas cambian de color (`:hover`) al pasar el cursor sobre ellas.
* **Selección Persistente:** Al hacer clic en una estrella, la calificación se fija y persiste en la interfaz.
* **Feedback Visual:** La calificación seleccionada se mantiene coloreada, proporcionando una retroalimentación clara al usuario.
* **Código Limpio:** Implementación directa y concisa en `main.js`.

## 🛠️ Tecnologías Utilizadas

* **HTML5:** Estructura del componente.
* **CSS3:** Estilos visuales y el efecto *hover*.
* **JavaScript (Vanilla JS):** Lógica para gestionar los eventos `mouseover`, `mouseout`, y `click` en las estrellas.

## 🚀 Cómo Empezar

Para usar este widget en cualquier proyecto o para verlo en funcionamiento:

1.  **Clonar el Repositorio:**
    ```bash
    git clone [https://github.com/romagaco/rating](https://github.com/romagaco/rating)
    cd rating
    ```
2.  **Abrir el Archivo:** Simplemente abre el archivo `index.html` en tu navegador web.

La lógica está autocontenida y se inicializa al cargar la página (`main.js`).

## ⚙️ Estructura del Código

El corazón de la aplicación reside en el manejo de tres eventos principales en `main.js`:

| Evento | Función | Descripción |
| :--- | :--- | :--- |
| `mouseover` | `hoverHandler()` | Pinta las estrellas desde la primera hasta la que está siendo apuntada. |
| `mouseout` | `unhoverHandler()` | Restaura las estrellas a la calificación previamente seleccionada (`currentRating`). |
| `click` | `clickHandler()` | Fija la calificación actual (`currentRating`) y la almacena. |

### Lógica Clave

El truco de la implementación reside en la función que colorea las estrellas, la cual se llama en los tres eventos (`hover`, `unhover`, `click`):

1.  Cada estrella se selecciona usando `querySelectorAll`.
2.  La calificación (índice) se utiliza para iterar sobre la lista de estrellas.
3.  Todas las estrellas cuyo índice es **menor o igual** al índice de la estrella actual se les añade la clase CSS que les da color (`.star-checked`).
4.  Todas las estrellas restantes son despojadas de esa clase.

De esta manera, la misma lógica se reutiliza para pintar las estrellas en el *hover* (temporalmente) y en el *click* (permanentemente).