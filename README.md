# Primer entrega proyecto final - Coderhouse

Implementar un servidor de aplicación basado en Node.js y el módulo express. El servidor implementará dos conjuntos de rutas agrupadas en routers, uno con la url base '/productos' y el otro con '/carrito'. El puerto de escucha será el 8080 para desarollo y process.env.PORT para producción.

### Aspectos a incluir en el entregable

1. El router base '/api/productos' implementará cuarto funciones:

        a. GET:'/:id' - Listar todos los productos disponibles o un producto por su id

        b. POST:'/' - Para incorporar productos al listado

        c. PUT:'/:id' - Actualiza un producto por su id

        d. DELETE:'/:id' - Borra un producto por su id
2.  El router base '/api/carrito' implementará tres rutas:

        a. POST:'/' - Crear un carrito y devuelve su id

        b. DELETE:'/:id' - Vacía el carrito y lo elimina

        c. GET:'/:id/productos' - Listar todos los productos guardados en el carrito

        d. POST:'/:id/productos' - Para incorporar productos al carrito por su id de producto

        e. DELETE:'/:id/productos/:id_prod' - Elimina un producto del carrito por su id de carrito y de producto
3. Crear una variable booleana administrador, cuyo valor configuraremos más adelante con el sistema de login. Según su valor me permitirá alcanzar o no las rutas indicadas. En el caso de recibir un request a una ruta no permitida por el perfil, devolver un objeto error. Ejemplo: {error : -1, descripcion: ruta 'x' método 'y' no autorizada }
4. Un producto dispondrá de los siguientes campos: id, timestamp, nombre, descripcion, codigo, foto (url), precio, stock
5. El carrito de compras tendrá la siguiente estructura: id, timestamp(carrito), productos: { id, timestamp(producto), nombre, descripcion, codigo, foto (url), precio, stock }
6. El timestamp puede implementarse con Date.now()
7. Realizar la persistencia de productos y del carrito de compras filesystem