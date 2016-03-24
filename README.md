# mongoose-statics
Simple add all CRUD methods and more to your Mongoose Models

## Usage in your mongoose model

mongooseSchema.statics = require('../modules/mongoose-statics');

## Example

## Methods

### $create

    User.$create({ name: 'John', age: 32 }, function(error, user) {
        console.log('User with ' + user.name + ' was created in the database');
    });

### $read

    User.$read({ age: 32 }, function(error, docs, numberFound) {
        console.log('Read ' + numberFound + ' documents.');
    });

### $readOne

    User.$readOne({ age: 32 }, function(error, doc) {
        console.log('User read with name = ' + user.name + ' from database');
    });

### $updateById

    User.$updateById(id, function(error, doc) {
        console.log('User updated');
    });

### $delete


