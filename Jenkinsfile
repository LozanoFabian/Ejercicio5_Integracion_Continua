def fechaNacimiento = 1990
def edad
def cadena

pipeline {
  agent any

  stages {
    stage('Calcular edad') {
      steps {
        script {
          year = new Date().getYear().toInteger()  
          print("La fecha actual es ${year}")
          edad = year - fechaNacimiento

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
          writeFile(file: "C:\\ProgramData\\Jenkins\\.jenkins\\workspace\\Ejercicio 5\\Edad.txt", text: cadena)
          println("El fichero fue escrito en")
        }
      }
    }
  }
}
