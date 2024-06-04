import java.text.SimpleDateFormat

salida = "El resultado de la ejecución es:"
numero1 = 100
numero2 = 200
ciudad = "Sevilla"

pipeline
{
    agent any
    environment
    {
        
        NOMBRE_ARCHIVO = "informacion_proceso.txt"

        
    }
    options
    {
    timeout(time:15, unit: "MINUTES") 
    }
    stages
    {
        stage("Saludo con fecha")
        {
            steps
            {
                script
                {
                    fecha = new Date()
                    formato = new SimpleDateFormat("dd/MM/yyyy")
                    fechaFormato = formato.format(fecha)
                    mensaje = ("\r¡Hola! \rBien venido a " + ciudad)
                    mensaje += ("\rLa fecha de hoy es:" + fechaFormato)
                    salida += "\r-----STAGE DE SALUDO-------"
                    salida += mensaje
                    println mensaje
                }
            }
        }
        stage("Suma")
        {
            steps
            {
                script
                {
                    suma = numero1+numero2
                    mensajesum = ("\rLa suma es : " + suma)
                    salida += "\r-----STAGE DE SUMA-------"
                    salida += mensajesum
                    println mensajesum
                    
                }
            }
        }
        stage("resta")
        {
            steps
            {
                script
                {
                    resta = numero1-numero2
                    mensajeresta =("\rLa resta es : " + resta)
                    println mensajeresta
                    salida += "\r-----STAGE DE RESTA-------"
                    salida += mensajeresta
                }
            }
        }
        stage("multiplicacion")
        {
            steps
            {
                script
                {
                    multip = numero1*numero2
                    mensajemultip =("\rEl producto es : " + multip)
                    println mensajemultip
                    salida += "\r-----STAGE DE PRODUCTO-------"
                    salida += mensajemultip
                }
            }
        }
         stage("division")
        {
            steps
            {
                script
                {
                    mensajecociente = (numero1 == 0 || numero2==0) ? ("\rNo se puede divdir por 0. \r Uno de los valoeres es 0.") : ("\rAmbos valores son mayores que 0. \rEl cociente es: " + (numero1 / numero2))
                    salida += "\r-----STAGE DE COCIENTE-------"
                    salida +=mensajecociente
                    println mensajecociente
                    
                }
            }
        }
        stage("Crear fichero")
        {
            steps
            {
                script
                {
					println "Se va a grabar en el fichero la siguiente cadena"+ salida
                    writeFile(file:NOMBRE_ARCHIVO, text:salida)
                }
            }
        }
    }
}
