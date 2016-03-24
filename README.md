# mongoose-statics
Simple add all CRUD methods and more to your Mongoose Models

## Usage in your mongoose model

mongooseSchema.statics = require('../modules/mongoose-statics');

## Example

## Methods

### $create

    User.$create({ name: 'John', age: 32}, function(error, user) {
        console.log('User with ' + user.name + ' was created in the database';
    });

### $read

### $readOne

### $update

### $delete


