# ALUCAR-
Aplicativo para empresa de aluguel de carros para motoristas de aplicativos


```mermaid
---
config:
  layout: dagre
---
erDiagram
	direction TB
	ALUGUEL {
		int id PK ""  
		date dataRetirada  ""  
		date dataDevolucao  ""  
		float valor  ""  
		string status  "ativo/finalizado"  
	}

	CARRO {
		string placa PK ""  
		string marca  ""  
		string modelo  ""  
		int ano  ""  
		string status  "disponível/indisponível"  
	}

	PAGAMENTO {
		int id PK ""  
		date data  ""  
		float valor  ""  
		string forma  "dinheiro/cartão/pix"  
	}

	CLIENTE {
		int id PK ""  
		string nome  ""  
		string cpf  ""  
		string telefone  ""  
		string email  ""  
		int idade  ""  
	}

	Funcionario {
		int id PK ""  
		string nome  ""  
		string PIS-NIT  ""  
	}

	garagem {
		string placa PK ""  
		string marca  ""  
		string modelo  ""  
		int ano  ""  
	}

	ALUGUEL}o--||Funcionario:"lança informações no sistema"
	ALUGUEL||--o{PAGAMENTO:"gera"
	Funcionario}|--|{CLIENTE:"atendido pelo"
	CARRO}o--|{garagem:"localiza carro na"
	garagem}|--|{ALUGUEL:"separa carro e manda informações pro"
	Funcionario}|--|{CARRO:"Verifica disponibilidade"

	classDef Pine :,stroke-width:1px, stroke-dasharray:none, stroke:#254336, fill:#27654A, color:#FFFFFF
```
