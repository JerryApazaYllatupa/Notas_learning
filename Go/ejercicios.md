# Resolviendo ejercicios con go

```go
	for i := n; i > 0; i-- {
		text := ""
		for j := int32(1); j <= n; j++ {
			if j >= i {
				text += "#"
			} else {
				text += " "
			}

		}
		fmt.Println(text)
	}
```

