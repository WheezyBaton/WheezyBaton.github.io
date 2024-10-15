### WheezyBaton.github.io

#Zadanie 16. Oblicz prawdopodobieństwo, że zmienna lodowa X o rozkładzie dwumianowym
#B(100, 1/4) przyjmuje wartość 25. Oblicz to samo prawdopodobieństwo dla zmiennej
#losowej Y o rozkładzie Poissona z parametrem λ = 25. Porównaj prawdopodobieństwa, że
#zmienne losowe X i odpowiednio Y przyjmują wartości ze zbioru A = {10, 30, 50, 70}.
#B = (−∞, 30), C = [30, ∞). 

# Ustawienie parametrów
#n <- 100       # liczba prób
#p <- 1/4      # prawdopodobieństwo sukcesu
#lambda <- 25  # parametr Poissona

# 1. Obliczenie prawdopodobieństwa P(X = 25)
#P_X_25 <- dbinom(25, n, p)

# 2. Obliczenie prawdopodobieństwa P(Y = 25)
#P_Y_25 <- dpois(25, lambda)

# Obliczenie prawdopodobieństwa, że X przyjmuje wartość 25
# Rozkład dwumianowy B(100, 1/4)
PX25 <- dbinom(25, 100, 0.25)

# Obliczenie prawdopodobieństwa, że Y przyjmuje wartość 25
# Rozkład Poissona z parametrem λ = 25
PY25 <- dpois(25, 25)

# Obliczenie prawdopodobieństw dla zbioru A = {10, 30, 50, 70}
# Suma prawdopodobieństw dla X
PXA <- sum(dbinom(c(10, 30, 50, 70), 100, 0.25))
# Suma prawdopodobieństw dla Y
PYA <- sum(dpois(c(10, 30, 50, 70), 25))

# Obliczenie prawdopodobieństw dla zbioru B = (-∞, 30)
# P(X < 30)
PXB <- pbinom(30, 100, 0.25) - dbinom(30, 100, 0.25)
# P(Y < 30)
PYB <- ppois(30, 25) - dpois(30, 25)

# Obliczenie prawdopodobieństw dla zbioru C = [30, ∞)
# P(X >= 30)
PXC <- 1 - PXB
# P(Y >= 30)
PYC <- 1 - PYB

# Wyświetlenie wyników
cat("PX25: ", PX25, "\n")
cat("PY25: ", PY25, "\n")
cat("PXA: ", PXA, "\n")
cat("PYA: ", PYA, "\n")
cat("PXB: ", PXB, "\n")
cat("PYB: ", PYB, "\n")
cat("PXC: ", PXC, "\n")
cat("PYC: ", PYC, "\n")
