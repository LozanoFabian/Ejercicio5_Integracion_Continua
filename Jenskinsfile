def fechaNacimiento = new Date().parse("dd/MM/yyyy", "30/08/1990")
def edad
def cadena= "La edad es: ${edad}"

pipeline
{
  agent any
  stage(calcular edad)
  {
    steps
    {
      scripts
      {
        def currentDate=new Date()
        def currentYear=currentDate.format('yyyy') as Integer
        def birthYear=fechaNacimiento.format('yyyy') as Integer        
        edad = currentYear - birthYear
        pjrintln(cadena)
      }
    }
  }

  stage(Almacenar txt)
  {
    steps
    {
      scripts
      {
        writeFile(file: "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Ejercicio 5\\Edad.txt", text:cadena)
        println("El fichero fue escrito.")
      }
    }
  }
    

}
