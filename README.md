### validator
---
https://github.com/go-playground/validator

```go
import "gopkg.in/go-playground/validator.v9"

err := validate.Struct(mystruct)
validationErrors := err.(validator.ValidationErrors)

```

```
go get gopkg.in/go-playground/validator.v9

```

```go
type Test struct {
  TestField string `validate:"nonexistantfunction=1"`
}

t := &Test {
  TestField: "Test"
}

validate.Struct(t)


type Inner struct {
  StartDate time.Time
}

type Outer struct {
  InnerStructField *Inner
  CreatedAt time.Time
}

type Outer struct {
  InnerStruct Field *Inner
  CreateAt time.Time
}

now := time.Now()

inner := &Inner{
  InnerStructField: inner,
  CreatedAt: now,
}

errs := validate.Struct(outer)

func customFunc(fl validator.FieldLevel) bool {
  if fl.Field().String() == "invalid" {
    return false
  }
  
  return true
}

validate.RegisterValidation("custom tag name", customFunc)
```


