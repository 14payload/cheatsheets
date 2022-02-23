### show all properties of a specific computer object
```
Get-ADComputer <computer> -Properties *
```


### add a new value for the attribute "msDS-AllowedToDelegateTo" for a computer1 (Constrained Delegation)
```
Set-ADComputer -Identity <computer1> -Add @{'msDS-AllowedToDelegateTo'=@('foo/<computer2>','CIFS/<fqdnComputer2>')}
```

### remove (Constrained Delegation)
```
Get-ADComputer -Identity <computer1> | Set-ADAccountControl ‑TrustedToAuthForDelegation $false
Set-ADComputer -Identity <computer1> -Clear 'msDS-AllowedToDelegateTo'
```


### add a new value for the attribute "PrincipalsAllowedToDelegateToAccount" for a computer1 (Resource Constrained Delegation)
```
Set-ADComputer -Identity <computer1> -PrincipalsAllowedToDelegateToAccount (Get-ADComputer <computer2>)
```

### remove (Resource Constrained Delegation)
```
Set-ADComputer <computer1> -PrincipalsAllowedToDelegateToAccount $Null
```

