# sql-select-fundamentals
consultas_basicas.sql
## ¿Por qué es mala práctica usar SELECT * en producción?

Utilizar `SELECT *` devuelve todas las columnas de una tabla, aunque muchas de ellas no sean necesarias.

Esto puede generar varios problemas:

- **Rendimiento:** se transfieren más datos de los necesarios, aumentando el tiempo de ejecución de la consulta.
- **Mantenibilidad:** si la estructura de la tabla cambia y se agregan nuevas columnas, la consulta devolverá información que quizás no era necesaria.
- **Seguridad:** pueden exponerse datos sensibles que no deberían ser utilizados por determinados usuarios o procesos.

Por estas razones, en producción es recomendable seleccionar únicamente las columnas que realmente se necesitan.

---

## ¿Por qué son importantes los alias para un stakeholder no técnico?

Los alias permiten reemplazar nombres técnicos de las columnas por nombres más claros y fáciles de interpretar.

Por ejemplo:

```sql
SELECT total_amount AS monto_total
FROM sales;
