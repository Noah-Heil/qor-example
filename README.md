# QOR example application

This is an example application to show and explain features of [QOR](http://getqor.com).

Chat Room: [![Join the chat at https://gitter.im/qor/qor](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/qor/qor?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Quick Started

### Go version: 1.6+

```shell
# Get example app
$ go get -u github.com/qor/qor-example

# Setup database
$ mysql -uroot -p
mysql> CREATE DATABASE qor_example;

# Run Application
$ cd $GOPATH/src/github.com/qor/qor-example
$ go run main.go
```

### Generate sample data

```go
$ go run db/seeds/main.go db/seeds/seeds.go
```

### Run tests (Pending)

```
$ go test $(go list ./... | grep -v /vendor/ | grep  -v /db/)
```

### Compile golang templates to binary and run the application with the compiled templates.

Compile the templates:
```
go run main.go --compile-qor-templates
```

Run with compiled templates:
```
go run -tags 'bindatafs' main.go
```

If need be, to run normally again simply:
```
go run main.go
```

If you still have doubts or questions please refere to the documentation on BindataFS:
https://doc.getqor.com/plugins/bindata.html

Additionally if you are having issues with the resources showing up correctly you might consider looking in the following places:

deploy.sh
gulpfile.babel.js

and make sure you have the nodemodules and gulp installed if you want to make any changes on the front end:
Requires Node.js and Gulp for building frontend files

npm install && npm install -g gulp

    Watch SCSS/JavaScript changes: gulp


## Admin Management Interface

[Qor Example admin configuration](https://github.com/qor/qor-example/blob/master/config/admin/admin.go)

Online Demo Website: [demo.getqor.com/admin](http://demo.getqor.com/admin)

## RESTful API

[Qor Example API configuration](https://github.com/qor/qor-example/blob/master/config/api/api.go)

Online Example APIs:

* Users: [http://demo.getqor.com/api/users.json](http://demo.getqor.com/api/users.json)
* User 1: [http://demo.getqor.com/api/users/1.json](http://demo.getqor.com/api/users/1.json)
* Orders: [http://demo.getqor.com/api/orders.json](http://demo.getqor.com/api/orders.json)
* Products: [http://demo.getqor.com/api/products.json](http://demo.getqor.com/api/products.json)
* Product 1's ColorVariations [http://demo.getqor.com/api/products/1/color_variations.json](http://demo.getqor.com/api/products/1/color_variations.json)
* Product 1's ColorVariation 1 [http://demo.getqor.com/api/products/1/color_variations/1.json](http://demo.getqor.com/api/products/1/color_variations/1.json)

## License

Released under the MIT License.

[@QORSDK](https://twitter.com/qorsdk)
