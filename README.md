# schema-event-template

Repositorio template...

## A tener en cuenta

Se debe reemplazar del nombre:

1. En el directorio `lang/csharp` modificar el nombre de la carpeta `appname` con el respectivo.
2. Cambiar el nombre del cproj que se encuantra en la directorio `lang/csharp/Andreani/appname/Events` por el nombre que obtendra su librería de eventos, recomendamos siempre llamarla `Andreani.{appname}.Events`, reemplazando `{appname}` obviamente.
3. Modificar el contenido del cproj. Con los datos acordes a su librería

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
    <ImplicitUsings>enable</ImplicitUsings>
    <Nullable>enable</Nullable>
    <GeneratePackageOnBuild>True</GeneratePackageOnBuild>
    <Description>{descripcion}</Description>
    <PackageProjectUrl>{url del repositorio}</PackageProjectUrl>
    <RepositoryUrl>{url del repositorio}</RepositoryUrl>
    <PackageTags>eventos; esquemas; avro;</PackageTags>
    <Authors>{Autores responsables}</Authors>
    <Company>Andreani</Company>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Apache.Avro" Version="1.10.2" />
  </ItemGroup>
</Project>
```

4. Modificar el contenido del archivo `.github/workflows/publish.yml`, se debe proporcionar los correctos nombres de el directorio y el archivo avdl que se construira.

```yml
env:
  DIRECORY_SRC: 'lang/csharp/Andreani/{appname}/Events' # working directory remplace {appname}
  FILE_IDL: 'idl/{Example}.avdl' # archivo avdl remplace {Example}
```

## Comentarios

1. El template dispone de el jar de avro para permitir hacer pruebas localmente.
2. Solo es necesario subir archivos avdl, no es necesario que se suban los archivos c# o avpr o avsc
3. Cualquier duda con respecto a los esquemas dirijase a [Docs](https://architecture-it.github.io/docs/) o [Schemas](https://architecture-it.github.io/amqstreams-implementation/Schemas/schemas/)