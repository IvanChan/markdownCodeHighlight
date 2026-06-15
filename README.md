## JavaScript
```javascript
// arrow fn, template literal, destructuring
const greet = async ({ name = "World" }) => {
  const n = 0x1F + 3.14;          /* hex + float */
  let arr = [1, 2, 3].map(x => x ** 2);
  return `Hello, ${name}! ${n}`;
};
class Foo extends Bar { #priv = true; }
```

## HTML
```html
<!DOCTYPE html>
<html lang="en">
  <!-- comment -->
  <head><meta charset="utf-8"><title>Demo</title></head>
  <body>
    <a href="https://x.io" data-id='42'>Link &amp; text</a>
    <input type="text" disabled />
  </body>
</html>
```

## JSON
```json
{
  "name": "demo",
  "version": 1.5,
  "active": true,
  "tags": ["a", "b"],
  "meta": { "count": 0, "ratio": -3.2e1, "nil": null }
}
```

## C++
```cpp
#include <iostream>
template <typename T>
class Vec {
  T data[3];
public:
  // constructor
  Vec(T x) : data{x, x, x} {}
  T sum() const { return data[0] + data[1] + data[2]; }
};
int main() {
  auto v = Vec<double>(1.5);
  std::cout << v.sum() << '\n';
  return 0;
}
```

## Bash
```bash
#!/usr/bin/env bash
set -euo pipefail
NAME="${1:-world}"     # default arg
for i in {1..3}; do
  echo "Hi $NAME #$i" | tr a-z A-Z
done
if [[ -f "./file.txt" ]]; then cat ./file.txt; fi
```

## Java
```java
package demo;
import java.util.*;

public class Main {
    @Override
    public String toString() { return "obj"; }
    public static void main(String[] args) {
        var list = List.of(1, 2, 3);          // generics + var
        list.forEach(x -> System.out.println(x * 2L));
    }
}
```

## C
```c
#include <stdio.h>
#define MAX 100

typedef struct { int x, y; } Point;

int main(void) {
    Point p = {.x = 1, .y = 2};   /* designated init */
    for (int i = 0; i < MAX; i++) {
        printf("%d,%d\n", p.x, p.y);
    }
    return 0;
}
```

## Swift
```swift
import Foundation

struct User {
    let name: String
    var age: Int = 0
}
func greet(_ u: User) -> String {
    let msg = "Hi \(u.name), age \(u.age)"   // interpolation
    return msg
}
let users = [User(name: "Sam", age: 20)]
users.map { $0.age }.forEach { print($0) }
```

## Objective-C
```objc
#import <Foundation/Foundation.h>

@interface Greeter : NSObject
@property (nonatomic, copy) NSString *name;
- (NSString *)greet;
@end

@implementation Greeter
- (NSString *)greet {
    return [NSString stringWithFormat:@"Hi, %@! %d", self.name, 42];
}
@end
```

## Kotlin
```kotlin
data class User(val name: String, val age: Int = 0)

fun main() {
    val users = listOf(User("Sam"), User("Lee", 30))
    users.filter { it.age > 0 }
         .forEach { println("${it.name}: ${it.age}") }   // string template
    val sum = (1..10).sum()
}
```

## CSS
```css
:root { --main: #3498db; }
.btn, a:hover {
  color: var(--main);
  margin: 0 auto;
  font-size: 1.2rem;          /* comment */
  background: rgba(0, 0, 0, .5);
}
@media (max-width: 600px) { .btn { display: none; } }
```

## Python
```python
from dataclasses import dataclass

@dataclass
class User:
    name: str
    age: int = 0

def greet(u: User) -> str:
    nums = [x**2 for x in range(3) if x > 0]   # comprehension
    return f"Hi {u.name}, {nums}"

if __name__ == "__main__":
    print(greet(User("Sam", 20)))
```

## YAML
```yaml
# config file
name: demo
version: 1.5
enabled: true
tags: [a, b, c]
server:
  host: "127.0.0.1"
  ports:
    - 8080
    - 8443
desc: |
  multi-line
  text block
```

## Go
```go
package main

import "fmt"

type User struct {
    Name string
    Age  int
}

func main() {
    users := []User{{"Sam", 20}, {"Lee", 30}}
    for i, u := range users {        // range loop
        fmt.Printf("%d: %s=%d\n", i, u.Name, u.Age)
    }
}
```

## Rust
```rust
#[derive(Debug)]
struct User<'a> { name: &'a str, age: u32 }

fn greet(u: &User) -> String {
    let nums: Vec<i32> = (0..3).map(|x| x * 2).collect();
    format!("Hi {}, {:?}", u.name, nums)   // macro
}
fn main() {
    let u = User { name: "Sam", age: 20 };
    println!("{}", greet(&u));
}
```

## TypeScript
```typescript
interface User<T = string> {
  name: T;
  age?: number;          // optional
}
enum Role { Admin, User }

const greet = (u: User): string => {
  const r: Role = Role.Admin;
  return `Hi ${u.name}, role=${r}` as const;
};
class Service<T> implements Record<string, unknown> {
  [key: string]: unknown;
}
```
