# Observaciones

Mecha, felicitaciones por tu trabajo. Tu portfolio se ve muy lindo; me alegra ver que en general seguiste las pautas del diseño solicitado pero a la vez le diste tu toque personal. Me gustan muchisimo las imagenes e iconos elegidos, la tipografia de tu nombre, la eleccion de colores. Se nota, y aprecia, que hubo mucho trabajo para lograr una web que te represente y que sea amable con el usuario.

A nivel diseño, y sabiendo que siempre la estética de un sitio es una apreciación personal, creo que el mayor problema de tu web es que se ve algo "pegoteada", en el sentido de que muchas veces faltan algunos espacios que sí están en el diseño propuesto. Por darte un ejemplo de lo que quiero señalar, notá la distancia entre el titulo Mis Proyectos en el modelo de Ada vs el tuyo, que se ve siempre muy cerca de la seccion anterior y de las distintas tarjetas. Este tipo de pautas no son decisión nuestra como desarrolladores: vienen indicadas desde el diseño, y es necesario tratar de que sean lo mas fieles al modelo que podamos.

Te dejo varios comentarios para mencionar cositas puntuales. Como comentamos en clase, este trabajo no se hace para que constates conocimientos, sino para que aprendas: en ese sentido, mi intencion es que estos comentarios te sirvan para aprender, mejorar tu codigo a futuro e ir apreciando mejor qué se espera de nosotras como desarrolladoras front end.

## Estructura correcta de documento HTML

Tu HTML esta muy bien. Claro, prolijo, sin elementos de más, muy bien comentado. 

Utilizás ocasionalmente etiquetas `br` para separar las cosas: no llegué a comentarlo en clase, pero esto es incorrecto. Esa etiqueta es un resabio de viejas épocas en las cuales css no era tan poderoso como ahora, pero usarla hoy viola uno de los principios básicos de programación: la separación de responsabilidades. Los estilos se dan con css, la estructura se da con html. Una decisión de estilo como un espaciado entre dos elementos debe controlarse con css -flex, elementos en bloque, etc. 

Tenés cierta tendencia a tener divs de más. Algunas estructuras de tu web se podrían resolver con menos divs. Dicho esto, yo prefiero que los divs sobren antes de que falten: un div de más se soluciona muy fácil, un div menos puede ser un gran dolor de cabeza cuando estamos recién arrancando. Pero te invito a recorrer tu HTML pensando como eliminar algunos divs. 

Tenes ocasionalmente algunas estructuras que no tienen sentido. Por ejemplo:

```html
            <ul>
                <li>
                <a href=""class="lo-que-hago">LO QUE HAGO</a>
            </li>
            </ul>
```

"Ul" significa "lista desordenada". Esto no es una lista, es un unico elemento. Esto confundiria a un lector de pantalla y complica innecesariamente tu codigo. 

## Respeta la consigna 

- El portfolio cuenta con las secciones solicitadas 
- Al clickear en los links de navegación, debe llevar a la sección correspondiente
- Al clickear en los links de contacto, debe llevar a la página externa
correspondiente 

Cumplidos

- El portfolio debe tener un diseño responsivo y verse correctamente en distintos dispositivos 

No cumplido. Me esperaba por tu comentario que no anduviera el responsive del form, pero veo que directamente no funciona en ninguna resolucion. Veo en tu codigo el interes por hacerlo funcionar para celulares, pero quedó mucho trabajo pendiente ahí. 

Nota que escribiste: `@media (max-width: 320px) {`. Eso significa "cuando la pantalla mida como maximo 320px, estos van a ser los estilos". Y no funciona esto, porque los celulares tienen **como minimo** 320px, y como maximo 600px. La media deberia ser

`@media (min-width: 320px) and (max-width: 600px) {`

Fijate que con ese cambio, ya todo se ve un poco mejor en celulares, pero aun hay algo de trabajo por hacer. Tu formulario es una de las cosas que mejor queda! 

- A "presentacion" le das un width de 320px, lo que no tiene sentido. Queremos que ocupe el 100% de su ancho como haria normalmente. Sacale ese width y todo se acomodará mejor. 
- Las tarjetas de "Mis proyectos" no se ven centradas, y eso es porque a .container-mis-proyectos le falta un align-items: center en la media query

Una vez resuelto eso, me concentraria en hacer las media queries para que tambien se vea bien en tablets y escritorios pequeños. El responsive no es opcional: la mayoria de nuestros usuarios usaran nuestras webs en moviles, y es muy importante que manejes comodamente las media queries. 

- El portfolio debe estar deployado y ser accesible desde una URL 

No cumplido. En tu Readme me dejas la direccion "http://127.0.0.1:5500/index.html", eso no significa que este deployado en internet, esa url es la direccion local de tu computadora a la cual solo vos podes acceder. Repasá la clase donde deployamos en github pages o en netlify. 

- El repositorio en GitHub debe tener un readme adecuado 

Incumplido. Agradezco los cometarios a mi, pero el readme es público, y la idea es que lo lean potenciales empleadores y colegas: debes darle la bienvenida a ellos y contarles sobre tu proyecto. 

### Respeta el diseño dado 

Te alejás del diseño propuesto en varias ocasiones, generalmente con respecto al espaciado, y a veces no termino de ver si fue por elección, distracción, o porque no sabías como resolver algunas cosas. Más allá del motivo, las dejo comentadas con alguna ayuda para que puedas encarar su corrección si en algún momento querés hacerlo.

La barra de navegacion tiene un espaciado gigante arriba, porque le diste un height: 80px. Debe ser mas pequeño. 

La sección de presentación no tiene el espaciado indicado, ni la posición de los elementos. Notá que en la web modelo hay un generoso espacio alrededor del texto y de la imagen (padding), tanto a nivel horizontal como vertical - pensá en donde agregarlo para que quede mas similar al modelo. 

Entre la seccion de la cita y mis conocimientos hay un espacio en blanco, provocado porque la seccion cita tiene un margin innecesario: `margin-top: 20px;`. Dentro de la seccion cita hacen falta mas espaciados -con flex, margin o padding- entre los distintos elementos. 

Agrega espacios con padding entre las secciones, eso evita la barra blanca como la que comenté antes y ayuda a que tu web no se vea tan pegoteada. Mismo en el footer. 


### Buena estructura de proyecto 

Cumplido

### Código bien indentado 

No cumplido, tu tabulado está muy confuso. Recordá que siempre podés hacerlo automaticamente con VSCode haciendo click derecho + format document, pero yo te recomiendo que te acostumbres a tabular bien sola. Es muy importante para entender qué cosa está adentro de otra. Cada vez que abris una etiqueta, el contenido de esa etiqueta debe ir un espaciado hacia adentro. O sea, en lugar de esto:

```html
    <section id="mis-conocimientos">
        <div class="centrado-de-contenido-mis-conocimientos">
        <div class="titulo-mis-conocimientos">
        <h2>Mis conocimientos</h2>
        <p> Estos son las tecnologias a desarrollar durante la cursada de Ada Front -end Developer, en 8 modulos y alrededor de 123 clases.</p>
   
       </div>
    <div id="cards">
        <!-- contenido de cards, lo saco de aca para que no quede tan largo -->
     </div>
</div>
</section>
```
deberias tener esto:

```html
    <section id="mis-conocimientos">
        <div class="centrado-de-contenido-mis-conocimientos">
            <div class="titulo-mis-conocimientos">
                <h2>Mis conocimientos</h2>
                <p> Estos son las tecnologias a desarrollar durante la cursada de Ada Front -end Developer, en 8 modulos y alrededor de 123 clases.</p>
            </div>
             <div id="cards">
              <!-- contenido de cards, lo saco de aca para que no quede tan largo -->
            </div>
        </div>
    </section>
```

### Comentarios que permiten mejorar la legibilidad del código 

No cumplido en HTML. Es bueno separar cada seccion en HTML con comentarios, es mucho mas facil orientarse asi. 

### Uso correcto de etiquetas semánticas 

Cumplido en ocasiones. Tus links del footer son una nav igual que la de arriba, deberia estar indicado por esa etiqueta (esto es importante para accesibilidad). Ya te comenté que usaste una lista para el boton de la seccion principal, lo que no es correcto. Usas divs para las cards, aunque estrictamente deberian ser article. 

### Buenos nombres de clases 

En general está cumplido, pero junto con el comentario de reutilizar tus estilos, que te dejo mas abajo, vas a tener que dejar de hacer cosas como "card1, card2, card3". Deberian ser todas cards. La clase "form-control" no tiene sentido en tu codigo, a menos que haya salido del modelo de Ada no me explico por qué lo pusiste, ya que no hay controles de formulario en tu web, y el estilo que le agregas en css (position relative) no suma nada. 

### Código CSS bien estructurado 

Cumplido a nivel formal. Noto muchos estilos innecesarios o confusos, que te voy indicando en tu archivo de css. Pero te invito a que te tomes el ejercicio de repasar tu css viendo todas las cosas que se pueden sacar sin que impacte en tu codigo. 

### Reutilización de estilos 

No está cumplido este objetivo, ya que muchas veces repetís innecesariamente código css y no aprovechás correctamente la oportunidad de darle el mismo estilo a muchos elementos con la misma clase. Uso el siguiente caso como un ejemplo, pero no es la única vez en que podrías mejorar la reutilización. Considerá este código:

```css
.image-1,
.image-2,
.image-3 {
  margin: 0;
  border: 1px solid rgb(247, 29, 138);
  border-radius: 20px;
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  margin-left: 20px;
  margin-right: 20px;
}

.image-4,
.image-5,
.image-6 {
  margin: 0;
  border: 1px solid rgb(247, 29, 138);
  border-radius: 20px; 
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  margin-left: 20px;
  margin-right: 20px;
  margin-bottom: 20px;
}
```

Entiendo la idea de darle los mismos estilos a los tres nombres de clase, pero, por que separar 1 2 y 3 de 4, 5 y 6?? Son los mismos estilos, no tiene sentido separarlos. Pero mas alla de eso, si estos elementos tienen exactamente los mismos estilos, por que tienen distintos nombres de clase? La idea de las clases es justamente que todos los elementos que son iguales tengan el mismo nombre de clase. Podrías haberle dado a cada uno de esos elementos el mismo nombre, "conocimientos-card-img" por ejemplo, y sólo tendrías una clase para cada uno de ellos. No repetirnos a nosotras mismas es un principio muy importante en programación, porque en la repetición se encuentran buena parte de nuestros errores. Reutilizá tus clases siempre que puedas. 


### Cumple con criterios básicos de accesibilidad 

Eliminas el outline en el formulario, por lo que ese formulario no se puede recorrer con el teclado. Nunca nunca nunca elimines el outline a menos que lo reemplaces con otra cosa. 

- Los colores tienen un contraste adecuado 

Cumplido

- Las imágenes tiene el atributo `alt` que corresponde 

Tu imagen de la seccion cita tiene un alt, pero ninguna otra. Tu web debe ser accesible, y eso incluye tus imagenes: la mujer sentada en un banco que pones en la portada comunica algo a tus usuarios videntes, y debes encontrar la manera de transmitirle esa información a quienes no pueden verla. 

- Los íconos y elementos que no presentan texto agregan la información correspondiente por otros medios (etiquetas aria, texto oculto) 

No cumplido, por ejemplo en los links a redes sociales de tu footer. Necesitan un aria. 

- Los íconos y elementos que no necesitan ser anunciados por un lector de pantalla tienen la etiqueta aria
correspondiente 

No cumplido.

- Commits con mensajes adecuados 

Cumplido, noto muchos y buenos commits en tu proyecto, lo que siempre se agradece. 

- Cuenta con un favicon

No cumplido. 

### Nota: 7