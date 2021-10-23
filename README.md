# Javascript Bank Class

class Bank {
	constructor(accno, name, accType, balance) {
		this.accno = accno;
		this.name = name;
		this.accType = accType;
		this.balance = balance;
	}
	getBalance() {
		return `Your balance is $${this.balance}`;
	}
	withdraw(amt) {
		if (amt <= this.balance) {
			this.balance -= amt;
			return this.getBalance();
		} else {
			return 'Insufficient Funds';
		}
	}
	deposit(amt) {
		if (amt <= 499) {
			return 'Deposit minimum of $500';
		} else {
			this.balance += amt;
			return `$${amt} Deposited Successfully! ${this.getBalance()}`;
		}
	}
}

const Naresh = new Bank(50001, 'Naresh', 'Savings', '10000');
const Philomina = new Bank(50002, 'Philomina', 'Savings', '20000');
const Vaibhav = new Bank(50003, 'Vaibhav', 'Current', '30000');
const Pavithra = new Bank(50004, 'Pavithra', 'Current', '40000');

//console.log(Naresh.balance, Philomina, Vaibhav, Pavithra);
console.log(Pavithra.withdraw(20000));
console.log(Pavithra.deposit(50000));
