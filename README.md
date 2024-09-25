# GORM Oracle driver
## Description
📍 基于[sijms/go-ora](https://github.com/sijms/go-ora/)的纯Go Gorm Oracle 驱动

无需安装oracle客户端。

## DB Driver
[go-ora](https://github.com/sijms/go-ora)
A pure golang development of Oracle driver, do not need to install Oracle client.

## Quick Start
### how to install 
```bash
go get github.com/seelly/gorm-oracle
```
### usage
```go
import (
    "gorm.io/gorm"
    "oracle "github.com/seelly/gorm-oracle"
    "log"
)

//ORM bean
type TestBean struct {
	Id string `gorm:"column:ID;not null;primaryKey;size:36"`
	Field1 string `gorm:"column:FIELD1;size:255"`
	Field2 string `gorm:"column:FIELD2;size:255"`
	State string `gorm:"column:STATE;size:2"`
	CreateAt time.Time `gorm:"column:CREATE_AT"`
}

func main(){
    databaseURL := oracle.BuildUrl(server, port, service, user, password, nil)
    db, err := gorm.Open(oracle.Open(databaseURL),&gorm.Config{})
    if err != nil {
        log.Fatal(err)
    }
}
```
