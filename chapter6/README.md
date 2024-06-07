# Enums

```
enum IPAddrKind {
    V4,
    V6
}

fn main() {
    let four = IPAddrKind::V4;
    let siz = IPAddrKind::V6;
}

fn route(ip_type: IPAddrKind) {}

route(IPAddrKind::V4);
route(IPAddrKind::V6);
```


```
enum IPAddrKind {
    V4,
    V6
}

struct IPAddr {
    kind: IPAddrKind,
    address: String
}

let home = IPAddr {
    kind: V4,
    address: String::from("127.0.0.1"),
}

let loopback = IPAddr {
    kind: V6,
    address: String::from("::1"),
}
```

Another way to represent the above, just using enum

```
enum IPAddr {
    V4(String),
    V6(String),
}

let home = IPAddr::V4(String::from("127.0.0.1"))

let loopback = IPAddr::V6(String::from("::1"));
```

