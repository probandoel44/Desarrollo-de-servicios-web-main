# MiParqueo App: snapshot Desarrollo de servicios web

## Identificacion

- Repositorio: https://github.com/probandoel44/Desarrollo-de-servicios-web-main
- Rama revisada: `main`
- Commit base revisado: `3c1e47f7bff27e0b726f75c23dd4abfbe141bb1c`
- Los archivos estan dentro de `Desarrollo-de-servicios-web-main/`.
- Es un snapshot relacionado y no el repositorio canónico: https://github.com/probandoel44/Desarrollar-software-a-partir-de-la-integraci-n-de-sus-m-dulos-componentes

## Arquitectura observada

Esta copia usa Java 17, Spring Boot 2.5.14, Spring MVC, JPA, Thymeleaf, Bean Validation, MySQL Connector/J, Lombok y BCrypt. Contiene controladores web/API, servicios, repositorios, modelos y vistas. Las entidades incluyen usuarios, vehículos, puestos, reservas, movimientos, pagos, ubicación, fidelización y alertas.

Las rutas deben verificarse contra el commit canónico antes de declarar equivalencia. Una diferencia visible posible es que este snapshot no contiene los cambios de reservas por período publicados posteriormente en el candidato.

## Entradas y resultados

- Cliente/vehículos: recibe usuario autenticado y datos de vehículo o reserva según el controlador correspondiente.
- Reservas: debe comprobar vehículo propio, puesto, fechas y disponibilidad antes de persistir.
- Movimientos: recibe placa, tipo y cliente para ingreso/salida y genera pagos al registrar salida.
- Pagos: lista pagos y permite cambiar su estado según el módulo de esta copia.
- Usuarios: consulta/creación/edición/eliminación según la API o vistas disponibles.
- Alertas y fidelización: muestran y modifican entidades según sus controladores/repositorios.

El diagrama oficial de datos y el informe de aceptación no están incluidos. Los nombres exactos de entradas y estados deben contrastarse con el código y las pruebas de este commit.

## Evidencia SENA

| Elemento | Estado |
| --- | --- |
| Requerimientos | Pendiente: informe y `requerimientos.pdf` no están en el repositorio. |
| Acta de aprobación | Pendiente: no se encontró acta firmada. |
| Git | Disponible en GitHub, rama `main`, con commit base indicado. |
| Ejecutable | No hay JAR verificado para este commit. |
| URL desplegada | No hay URL pública verificada. |
| Pruebas | Las fuentes deben inspeccionarse y ejecutarse en una base aislada; no se atribuyen resultados sin ejecución real. |
| Base de datos | Spring/JPA y MySQL; revisar `application.properties` y el esquema antes de iniciar. |
| Ambientes | No se encontró perfil independiente de pruebas ni migraciones automatizadas. |
| Manual técnico | Esta guía describe módulos visibles; faltan resultados y aprobaciones oficiales. |

## Ejecución

Desde la carpeta `Desarrollo-de-servicios-web-main/`:

```powershell
.\mvnw.cmd spring-boot:run
```

Para construir:

```powershell
.\mvnw.cmd package
```

No confirmar el JAR ni el flujo integrado hasta verificar `target/*.jar`, base de datos, pruebas y rutas. No copiar credenciales reales a este archivo.

## Pendientes

1. Comparar este commit con el candidato canónico commit por commit.
2. Adjuntar informe y acta aprobada.
3. Generar JAR y documentar su nombre/ruta.
4. Ejecutar pruebas con base separada y guardar resultados.
5. Publicar URL real si existe una versión desplegada.
