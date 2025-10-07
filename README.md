# Base-DeDatosTest1
# 🏋️‍♂️ Fitness Tracker Database

Este proyecto define el esquema de una base de datos relacional para una aplicación de seguimiento de ejercicios, metas personales y áreas de enfoque físico. El modelo está diseñado para capturar relaciones entre usuarios, rutinas, categorías, y objetivos, permitiendo análisis personalizados y recomendaciones basadas en preferencias y rendimiento.

---

## 📐 Estructura de la Base de Datos

### 🗂️ Tablas Principales

#### `users`
Contiene información personal de cada usuario registrado.
- `id`: Identificador único
- `username`, `email`, `password`: Credenciales
- `photo_user`: Foto de perfil
- `birth_date`, `gender`, `weight`, `height`: Datos físicos
- `ranking`: Nivel o progreso
- `photo_categories`: Preferencia visual de categoría

#### `categories`
Define tipos de ejercicio o estilos de entrenamiento.
- `id`, `name`, `ranking`, `photo_categories`

#### `exercises`
Lista de ejercicios disponibles.
- `id`, `name`, `photo_exercise`, `ranking`, `photo_categories`

#### `focus_area`
Áreas del cuerpo o habilidades que se pueden entrenar.
- `id`, `name`, `photo_focus_area`

---

### 🔗 Tablas Relacionales

#### `user_exercise`
Registra cada sesión de ejercicio realizada por un usuario.
- `user_id`, `exercise_id`, `date`, `duration`

#### `user_focus`
Asocia usuarios con sus áreas de enfoque.
- `user_id`, `focus_area_id`

#### `user_category`
Relaciona usuarios con sus categorías preferidas.
- `user_id`, `category_id`

#### `exercises_focus`
Conecta ejercicios con las áreas que trabajan.
- `exercise_id`, `focus_area_id`

#### `user_goal`
Define metas personales del usuario.
- `user_id`, `goal`, `digital_goal`, `photo_goal`

---

## 🔒 Integridad Referencial

Todas las relaciones están reforzadas mediante claves foráneas para asegurar consistencia entre entidades:
- `user_id`, `exercise_id`, `focus_area_id`, `category_id` están conectados a sus respectivas tablas.
- Las claves foráneas están nombradas explícitamente para facilitar mantenimiento y depuración.

---

## 🚀 Posibles Extensiones

- Historial de progreso por área de enfoque
- Recomendaciones automáticas basadas en ranking y duración
- Integración con dispositivos de seguimiento físico

---

## 🧠 Uso Sugerido

Ideal para aplicaciones móviles o web que buscan:
- Personalizar rutinas de ejercicio
- Visualizar progreso físico
- Establecer y seguir metas de entrenamiento

---

## 📸 Notas Visuales

Las columnas `photo_*` permiten enriquecer la experiencia del usuario con imágenes representativas de ejercicios, metas, categorías y áreas de enfoque.

---

## 🧰 Tecnologías Recomendadas

- PostgreSQL o MySQL para implementación
- ORMs como Sequelize o Prisma para integración con backend
- APIs RESTful para interacción con frontend

---

## ✍️ Autor

Diseñado por Ernesto, con enfoque en modelado realista, integridad contextual y expansión iterativa.

