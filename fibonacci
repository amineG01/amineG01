import unittest


def fibonacci_numbers_below(limit):
   
    if not isinstance(limit, int) or limit <= 0:
        raise ValueError("Limit must be a positive integer.")
    
    actual = 1
    next_num = 2

    while actual < limit:
        yield actual
        actual, next_num = next_num, actual + next_num


def sum_of_even_fibonacci_numbers_below(limit):
   
    if not isinstance(limit, int) or limit <= 0:
        raise ValueError("Limit must be a positive integer.")

    return sum(num for num in fibonacci_numbers_below(limit) if num % 2 == 0)


class FibonacciNumbersTestCase(unittest.TestCase):
    def test_fibonacci_numbers_below_positive_limit(self):
        # Ensure positive limit generates Fibonacci numbers
        fibonacci = list(fibonacci_numbers_below(10))
        self.assertIn(1, fibonacci)
        self.assertIn(2, fibonacci)
        self.assertIn(3, fibonacci)
        self.assertIn(5, fibonacci)
        self.assertIn(8, fibonacci)

    def test_sum_of_even_fibonacci_numbers_below_positive_limit(self):
        # Ensure positive limit calculates sum of even Fibonacci numbers correctly
        self.assertEqual(10, sum_of_even_fibonacci_numbers_below(10))
        self.assertEqual(44, sum_of_even_fibonacci_numbers_below(100))

    def test_fibonacci_numbers_below_non_integer_limit(self):
        # Ensure ValueError is raised for non-integer limit
        with self.assertRaises(ValueError):
            fibonacci_numbers_below(10.5)

    def test_sum_of_even_fibonacci_numbers_below_non_integer_limit(self):
        # Ensure ValueError is raised for non-integer limit
        with self.assertRaises(ValueError):
            sum_of_even_fibonacci_numbers_below(10.5)


if __name__ == '__main__':
    unittest.main()
