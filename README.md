# mongoose-statics
Simple add all CRUD methods and more to your Mongoose Models!

The library makes the use of Promises. Simple learn promises byu watching this video: https://youtu.be/g90irqWEqd8

## Usage in your mongoose model

mongooseSchema.statics = require('../modules/mongoose-statics');

## Promise pattern

First you state what you want to do:

    User._create({ name: 'John', age: 32 })

Then, you simply pass on the values to the callback, if succeeded:

        .then(function(user) {
            console.log('User with ' + user.name + ' was created in the database');
        })

Or catch the errors on the way:

        .catch(function(error) {
            console.log('Error: ' + error);
        })

## Chaining promises

You can easily chain the different methods together:

User._read({})
    .then(function(result) {
        console.log('There are ' + result + ' documents in the database.';
        return User._create({ name: 'Misha', age: 7});
    })
    .then(function(user) {
        console.log('New user created: ' + user);
        return User._read({});
    })
    .then(function(result) {
        console.log('There are now ' + result + ' documents in the database.';
    })
    .catch(function(error) {
        console.log('There was an error in this chain: ' + error);
    });

## Example Schema declaration

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
        .then(function(user) {
            console.log('User with ' + user.name + ' was created in the database');
        });

### _read

    User._read({ age: 32 )
        .then(function(docs) {
            console.log('Read ' + docs.length + ' documents.');
        });

### _delete

    User._delete({ age: 32 )
        .then(function(result) {
            console.log(result + ' document(s) deleted.');
        });

