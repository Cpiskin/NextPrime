FUNCTION isPrime(num):
    IF num < 2 THEN
        RETURN false
    END IF
    FOR i FROM 2 TO sqrt(num):
        IF num % i == 0 THEN
            RETURN false
        END IF
    END FOR
    RETURN true

FUNCTION nextPrime(n):
    WHILE true DO
        n++
        IF isPrime(n) THEN
            RETURN n
        END IF
    END WHILE

FUNCTION main():
    CREATE Scanner object
    PRINT "Enter five integers (0 < n ≤ 500,000,000):"
    FOR i FROM 1 TO 5 DO
        READ num from user
        IF num > 0 AND num ≤ 500000000 THEN
            result = nextPrime(num)
            PRINT "Next prime greater than " + num + " is: " + result
        ELSE
            PRINT "Input out of range. Please enter a valid integer."
        END IF
    END FOR
    CLOSE Scanner
END FUNCTION
