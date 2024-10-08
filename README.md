def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def fahrenheit_to_kelvin(fahrenheit):
    return (fahrenheit - 32) * 5/9 + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def kelvin_to_fahrenheit(kelvin):
    return (kelvin - 273.15) * 9/5 + 32

def convert_temperature(value, unit):
    if unit.lower() == 'celsius':
        fahrenheit = celsius_to_fahrenheit(value)
        kelvin = celsius_to_kelvin(value)
        return fahrenheit, kelvin
    elif unit.lower() == 'fahrenheit':
        celsius = fahrenheit_to_celsius(value)
        kelvin = fahrenheit_to_kelvin(value)
        return celsius, kelvin
    elif unit.lower() == 'kelvin':
        celsius = kelvin_to_celsius(value)
        fahrenheit = kelvin_to_fahrenheit(value)
        return celsius, fahrenheit
    else:
        return None, None

def main():
    try:
        temperature = float(input("Enter the temperature value: "))
        unit = input("Enter the unit of measurement (Celsius, Fahrenheit, Kelvin): ").strip().lower()
        
        celsius, fahrenheit, kelvin = None, None, None
        
        if unit == 'celsius':
            fahrenheit, kelvin = convert_temperature(temperature, 'celsius')
            print(f"{temperature} Celsius is {fahrenheit:.2f} Fahrenheit and {kelvin:.2f} Kelvin")
        elif unit == 'fahrenheit':
            celsius, kelvin = convert_temperature(temperature, 'fahrenheit')
            print(f"{temperature} Fahrenheit is {celsius:.2f} Celsius and {kelvin:.2f} Kelvin")
        elif unit == 'kelvin':
            celsius, fahrenheit = convert_temperature(temperature, 'kelvin')
            print(f"{temperature} Kelvin is {celsius:.2f} Celsius and {fahrenheit:.2f} Fahrenheit")
        else:
            print("Invalid unit. Please enter Celsius, Fahrenheit, or Kelvin.")
    6
    except ValueError:
        print("Invalid input. Please enter a valid number for temperature.")

if __name__ == "__main__":
    main()



How It Works:
Conversion Functions: The program defines separate functions to handle conversions between Celsius, Fahrenheit, and Kelvin.

Conversion Logic: The convert_temperature function takes a temperature value and its unit, then converts it to the other two units.

User Interaction: The main function prompts the user for input, calls the conversion functions, and displays the results.

Error Handling: The program includes basic error handling for invalid inputs.
