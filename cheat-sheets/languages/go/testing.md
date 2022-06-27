## Libraries
```go
import (
	"testing"

	"github.com/stretchr/testify/require"
)

func TestFibonacci(t *testing.T) {
	expected := 0
	actual := compute(0)
	require.Equal(t, expected, actual)
}

```
## Parameterized Tests

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
