# loopback-datasource-juggler

An ORM/ODM that provides a common set of interfaces for interacting with databases, REST APIs, and other types of data sources. It was originally forked from [JugglingDB](https://github.com/1602/jugglingdb).

# 6 River Changes

This fork has the following changes:

* Uses our custom datasource-connector which supports more complex `where` clauses based on joins.
* adds the ability to do complex order_bys clauses:

```
   filter {where: {qty: {gt: 0}}, 
   order: {user: {name: 'asc'}}}
```

generates:

`select * from orders join orders.user_id = users.id where orders.qty > 0 order by users.name`


## Usage

Install Juggler:

```
npm install loopback-datasource-juggler
```

Then install a connector:

```
npm install loopback-connector-mongodb // in this case, the mongodb connector
```

## Documentation

See the [official documentation](http://docs.strongloop.com).

### Creating data sources programmatically

See [Advanced topics: data sources](http://docs.strongloop.com/display/LB/Advanced+topics%3A+data+sources). 
