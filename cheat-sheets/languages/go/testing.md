# Parameterized Tests

```go
import "testing"

func TestFibonacci(t *testing.T) {
	parameters := []struct {
		name string
		input, expected int
	}{
		{"golden path test", 0, 0},
		{"exceptional test a", 1, 1},
		{"exceptional test b" 2, 1},
	}

	for i := range parameters {
		actual := compute(parameters[i].input)
		if actual != parameters[i].expected {
			t.Logf("expected%d: , actual:%d", parameters[i].expected, actual)
			t.Fail()
		}
	}
}

func compute(n int) int {
	result := 0
	if n <= 1 {
		result = n
	} else {
		result = compute(n-1) + compute(n-2)
	}
	return result
}
```
