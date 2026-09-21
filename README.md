# DP-800 Lab 01: Diseño e implementación de bases de datos con SQL

⏱️ **Tiempo estimado:** 30 minutos

## 🎯 Objetivo
Diseñar el esquema de una plataforma e-commerce implementando tablas, restricciones, historial de datos, almacenamiento JSON y particionamiento usando SQL Server 2025+.

## 📝 Resumen de Pasos

1. **Configuración del Entorno:** Clonar el repositorio `mslearn-sql-developer` desde GitHub usando Visual Studio Code.
2. **Crear la Base de Datos:** Crear la base de datos `EcommerceDB` desde SSMS y conectarse a ella.
3. **Tablas Base y Restricciones:** Crear las tablas `Supplier`, `Category` y `Product` definiendo Primary Keys, Foreign Keys, índices y restricciones `CHECK` (precio > 0, stock >= 0).
4. **Tabla Temporal (Historial):** Crear la tabla `ProductPrice` con `SYSTEM_VERSIONING = ON` para guardar un registro automático de todos los cambios de precio a lo largo del tiempo.
5. **Almacenamiento JSON:** Añadir una columna tipo JSON a los productos para metadatos, extraer atributos (como el color) mediante columnas calculadas y crear un índice sobre ellas para acelerar búsquedas.
6. **Particionamiento de Datos:** Crear una función y esquema de partición por fechas (trimestres) para dividir la tabla de pedidos (`Order`), mejorando el rendimiento.
7. **Uso de SEQUENCE:** Crear un objeto `SEQUENCE` independiente para autogenerar los IDs de la tabla `OrderDetail` al insertar nuevos registros.
8. **Validación:** 
   * Intentar insertar un precio negativo (debe fallar).
   * Consultar atributos extraídos del JSON.
   * Usar `$PARTITION` para verificar la distribución de pedidos.
   * Consultar el historial de precios con `FOR SYSTEM_TIME ALL`.
9. **Limpieza (Opcional):** Eliminar la base de datos `EcommerceDB` marcando la opción de cerrar conexiones existentes.
