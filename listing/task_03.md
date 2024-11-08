Что выведет программа? Объяснить вывод программы. Объяснить внутреннее устройство интерфейсов и их отличие от пустых интерфейсов.

```go
package main

import (
	"fmt"
	"os"
)

func Foo() error {
	var err *os.PathError = nil
	return err
}

func main() {
	err := Foo()
	fmt.Println(err)
	fmt.Println(err == nil)
}
```

Ответ:
```
nil и false

nil - так как значение в интерфейсе не инициализовано
false - так как интерфейс состоит из значения типа для интерфейса и типом данных, реализующим этот интерфейс, но так как тип данных в интерфейсе есть, то и интерфейс не равен nil

Интерфейс представляет сообой копию данных и указатель на тип, который реализует интерфейс. Указатель на тип содержит методы, которые реализует тип данных.
Пустой интерфей не содержит указатель на тип данных, так как он соответствует любому типу, но содержит копию данных.

```