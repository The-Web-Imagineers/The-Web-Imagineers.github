VSCodeTriageBot/testissues
@Victorkeenom1
!-- -Victorkeenom Teams-background_MS-Ignite_v02_B (1) -VictorKeenom- !-- Please read our Rules of Conduct: https://opensource.microsoft.com/codeofconduct/ -- !-- 🕮 Read our guide about submitting -: https://github-com/microsoft/vscode/wiki/Submitting-Bugs-and-Suggestions ...

# A function to check if a number is prime
def is_prime(num):
    # If the number is less than 2, it's not prime
    if num < 2:
        return False
    # Check for factors up to the square root of the number
    for i in range(2, int(num**0.5) + 1):
        # If the number is divisible by any other number, it's not prime
        if num % i == 0:
            return False
    # If no factors were found, the number is prime
    return True

# Test the function with some example numbers
print(is_prime(5))  # Output: True
print(is_prime(10)) # Output: False
print(is_prime(23)) # Output: True
This code defines a function is_prime that checks if a given number is prime. It iterates through numbers up to the square root of the input number and checks if any of them divide evenly into the input number. If none do, the number is prime. This is a useful utility function that can be used in various scenarios where prime numbers are involved, such as cryptography, algorithms, or mathematical computations.




