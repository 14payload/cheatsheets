### Source
https://github.com/projectdiscovery/nuclei  

### Install
```
go install -v github.com/projectdiscovery/nuclei/v2/cmd/nuclei@latest
```

### Scan single host using default templates
```
nuclei -u <rhost> -o <file>
```

### Scan list of hosts using single template
```
nuclei -l <rhostsFile> -t osint/<template>.yaml -o <file>
```

### Execute only osint tempaltes
```
nuclei -tags osint -var user=<user> -o <file>
```

### List available templates
```
nuclei -tl
```

