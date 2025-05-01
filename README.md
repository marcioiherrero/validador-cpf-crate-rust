Instalação:
-----------
No arquivo Cargo.toml de seu projeto, adicionar a dependência na seção: "dependencies" como abaixo:
```rust
[dependencies]
validador_cpf_mih = "0.1.0"
```

Exemplo de utilização:
----------------------
```rust
use validador_cpf_mih as vd;
use std::io;

fn main() {
  println!("Digite o cpf: ");
  let mut cpf = String::new();
  match io::stdin().read_line(&mut cpf) {
    Ok(_) => {
      println!("Você digitou: {}", cpf.trim());
    },
    Err(e) => {
      println!("Erro ao ler entrada: {}", e);
    }
  }
  
  let validado = vd::validar_cpf(cpf.as_str());
  
  if validado {
    println!("O CPF é válido.");
  } else {
    println!("O CPF é inválido.");
  }
}
```
