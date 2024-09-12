# CURSO: APRENDE BLAZOR

# LECCIÓN 35: Atributo SupplyParameterFromQuery

1. Abrir la aplicación con Visual Studio 2022 o VSCode

2. El atributo [SupplyParameterFromQuery] enlaza el parámetro de un componente con el valor "query string" de una determinada ruta URL

```razor
@page "/queryparameter"

@* https://localhost:7111/queryparameter?name1=John *@
@* https://localhost:7111/queryparameter?name1=John&name2=Lucas *@

<h3>Hello, @Name1 @Name2</h3>

@code {
    [Parameter]
    [SupplyParameterFromQuery(Name = "name1")]
    public string Name1 { get; set; } = "Unknown";

    [Parameter]
    [SupplyParameterFromQuery(Name = "name2")]
    public string Name2 { get; set; } = "Unknown";
}
```

3. Ahora navegamos a la siguiente dirección: /queryparameter?name=John

4. En el NavMenu.razor también podemos enlazarlo a la URL del punto 3

```razor
 <div class="nav-item px-3">
     <NavLink class="nav-link" href="/queryparameter?name1=John">
         <span class="bi bi-list-nested-nav-menu" aria-hidden="true"></span> Nuevo Componente 1
     </NavLink>
 </div>

 <div class="nav-item px-3">
     <NavLink class="nav-link" href="/queryparameter?name1=John&name2=Lucas">
         <span class="bi bi-list-nested-nav-menu" aria-hidden="true"></span> Nuevo Componente 2
     </NavLink>
 </div>
```

5. Como resultado obtenemos el mensaje: Hello, John!
 
