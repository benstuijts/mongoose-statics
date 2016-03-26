# mongoose-statics
Simple add all CRUD methods and more to your Mongoose Models!

The library makes the use of Promises.

## Usage in your mongoose model

mongooseSchema.statics = require('../modules/mongoose-statics');

## Example

    var mongoose = require('mongoose');
    var userSchema = mongoose.Schema({
        name: String,
        age: Number,
        admin: { type: boolean, default: false }
    });
    userSchema.statics = require('../modules/mongoose-statics');
    module.exports = mongoose.model('User', userSchema);

## Methods

### _create

    User._create({ name: 'John', age: 32 })
        .then(
            console.log('User with ' + user.name + ' was created in the database');
        );

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


