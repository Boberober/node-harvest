Harvest is a tool that enables businesses to track time, track projects, manage clients, and invoice. This is a full client API built using node.js.

# Install

    npm install harvest

# Usage

    var Harvest = require('harvest')
        , harvest = new Harvest({
            subdomain: config.harvest.subdomain,
            email: config.harvest.email,
            password: config.harvest.password
        })
        TimeTracking = harvest.TimeTracking;

    TimeTracking.daily({}, function(err, tasks) {
        if (err) throw new Error(err);

	// work with tasks
    });

# Testing

In order to test you will need to create a config file that uses your credentials inside `config/default.json`

    {
      "harvest": {
        "subdomain": "...",
        "email": "...",
        "password": "...",
        "identifier": "...",
        "secret": "...",
        "user_agent": "node-harvest test runner"
      }
    }

This API is designed to work either using HTTP Basic authentication, or OAuth so either set of credentials will work. Subdomain is always required.

## Running the tests

    npm test

    # or

    mocha

## Projects using this library

- [impleri/sow](https://github.com/impleri/sow): Command line time tracking utility
