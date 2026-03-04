# Calculadora 
def calculadora():
    historial = []  # Lista para guardar operaciones

    while True:
        print("\nCalculadora básica")
        print("1. Suma")
        print("2. Resta")
        print("3. Multiplicación")
        print("4. División")
        print("5. Ver historial")
        print("6. Salir")

        opcion = input("Ingrese una opción (1-6): ")

        if opcion in ['1', '2', '3', '4']:
            try:
                num1 = float(input("Ingrese el primer número: "))
                num2 = float(input("Ingrese el segundo número: "))
            except ValueError:
                print("Error: Debe ingresar números válidos.")
                continue

            if opcion == '1':
                resultado = num1 + num2
                print(f"{num1} + {num2} = {resultado}")
                historial.append(f"{num1} + {num2} = {resultado}")
            elif opcion == '2':
                resultado = num1 - num2
                print(f"{num1} - {num2} = {resultado}")
                historial.append(f"{num1} - {num2} = {resultado}")
            elif opcion == '3':
                resultado = num1 * num2
                print(f"{num1} * {num2} = {resultado}")
                historial.append(f"{num1} * {num2} = {resultado}")
            elif opcion == '4':
                if num2 != 0:
                    resultado = num1 / num2
                    print(f"{num1} / {num2} = {resultado}")
                    historial.append(f"{num1} / {num2} = {resultado}")
                else:
                    print("Error: No se puede dividir por cero.")

        elif opcion == '5':
            print("\n--- Historial ---")
            if historial:
                for operacion in historial:
                    print(operacion)
            else:
                print("No hay operaciones realizadas aún.")

        elif opcion == '6':
            print("Saliendo de la calculadora...")
            break

        else:
            print("Opción inválida, intente nuevamente.")

calculadora()
