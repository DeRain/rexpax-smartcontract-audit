# Компиляция смарт контракта
Контракт компилируется без ошибок

# Отчет Oyente Tool по безопасности смарт контрактов

(https://github.com/melonproject/oyente)[https://github.com/melonproject/oyente]  

Исходя из отчета можно сделать вывод, что контракт не подвержен общим уязвимостям безопаности,  
связанными со спецификой работы EVM и сети Ethereum.

```bash
root@f58ce95b7b27:/oyente/oyente# python oyente.py -gtc -a -s /contracts/crowsale.sol
WARNING:root:You are using evm version 1.7.1. The supported version is 1.6.6
INFO:root:Contract /contracts/crowsale.sol:Rexpax:
INFO:symExec:Running, please wait...
INFO:symExec:	============ Results ===========
INFO:symExec:	  EVM Code Coverage: 	 95.4%
INFO:symExec:	  Callstack Depth Attack Vulnerability:  False
INFO:symExec:	  Transaction-Ordering Dependence (TOD): False
INFO:symExec:	  Timestamp Dependency: 		 False
INFO:symExec:	  Re-Entrancy Vulnerability: 		 False
INFO:symExec:	  Assertion Failure: 			 True
INFO:symExec:/contracts/crowsale.sol:36:9: Warning: Assertion Failure.
        assert(a >= b)
Assertion violates when:
    _value = 2
    balances[this] = 115792089237316195423570985008687551041346808175670299467965221634129033953278
    totalSupply = 1
    owner = 0
/contracts/crowsale.sol:42:9: Warning: Assertion Failure.
        assert(c >= a && c >= b)
Assertion violates when:
    startTime = 57896044618658097711776297531098758593484842250657380164627079569223463184256
    contract_state = 1
INFO:root:Contract /contracts/crowsale.sol:SafeMath:
INFO:symExec:Running, please wait...
INFO:symExec:	============ Results ===========
INFO:symExec:	  EVM Code Coverage: 	 100.0%
INFO:symExec:	  Callstack Depth Attack Vulnerability:  False
INFO:symExec:	  Transaction-Ordering Dependence (TOD): False
INFO:symExec:	  Timestamp Dependency: 		 False
INFO:symExec:	  Re-Entrancy Vulnerability: 		 False
INFO:symExec:	  Assertion Failure: 			 False
INFO:symExec:	====== Analysis Completed ======
INFO:symExec:	====== Analysis Completed ======
```
