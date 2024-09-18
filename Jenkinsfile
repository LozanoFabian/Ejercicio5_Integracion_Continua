def fechaNacimiento = new Date().parse("dd/MM/yyyy", "30/08/1990")
def edad
def cadena

pipeline {
  agent any

  stages {
    stage('Calcular edad') {
      steps {
        script {
          def currentDate = new Date()
          def currentYear = currentDate.format('yyyy') as Integer
          def birthYear = fechaNacimiento.format('yyyy') as Integer        
          edad = currentYear - birthYear

          // Actualiza la cadena después de calcular la edad
          cadena = "La edad es: ${edad}"
          println(cadena)  // Imprimir la cadena en la consola
        }
      }
    }

    stage('Almacenar txt') {
      steps {
        script {
          // Almacenar el archivo en el directorio del workspace de Jenkins
          def workspace = pwd()  // Obtener el directorio del workspace
          writeFile(file: "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Ejercicio 5\\Edad.txt", text: cadena)
          println("El fichero fue escrito en")
        }
      }
    }
  }
}
