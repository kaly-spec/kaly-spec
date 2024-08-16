def calcular_imc(peso, altura):
    """
    Calcula el Índice de Masa Corporal (IMC).
    
    Parámetros:
    peso (float): El peso de la persona en kilogramos.
    altura (float): La altura de la persona en metros.
    
    Retorna:
    float: El IMC calculado.
    """
    if altura <= 0:
        raise ValueError("La altura debe ser mayor que cero.")
    return peso / (altura ** 2)

def clasificar_imc(imc):
    """
    Clasifica el IMC en categorías.
    
    Parámetros:
    imc (float): El IMC a clasificar.
    
    Retorna:
    str: La categoría correspondiente del IMC.
    """
    if imc < 18.5:
        return "Bajo peso"
    elif 18.5 <= imc < 24.9:
        return "Normal"
    elif 25 <= imc < 29.9:
        return "Sobrepeso"
    else:
        return "Obesidad"

def main():
    """
    Función principal que ejecuta el programa.
    """
    try:
        peso = float(input("Introduce tu peso en kilogramos: "))
        altura = float(input("Introduce tu altura en metros: "))
        
        imc = calcular_imc(peso, altura)
        categoria = clasificar_imc(imc)
        
        print(f"Tu IMC es {imc:.2f}")
        print(f"Categoría: {categoria}")
        
    except ValueError as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()
