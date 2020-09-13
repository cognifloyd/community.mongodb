# Mongodb Collection
|Category|Status|
|---|---|
|Github CI|![CI](https://github.com/ansible-collections/community.mongodb/workflows/CI/badge.svg)|
|Github Docs|![documentation](https://github.com/ansible-collections/community.mongodb/workflows/documentation/badge.svg)|
|Codecov|[![Codecov](https://img.shields.io/codecov/c/github/ansible-collections/community.mongodb)](https://codecov.io/gh/ansible-collections/community.mongodb)|
|Travis MongoDB Roles|[![Travis Status](https://travis-ci.com/ansible-collections/community.mongodb.svg)](https://travis-ci.com/ansible-collections/community.mongodb)|
|MongoDB Clusters|[![Build Status](https://travis-ci.com/rhysmeister/AutomatingMongoDBWithAnsible.svg?token=EZq8qB3ASZpTwAxAkbiU&branch=master)](https://travis-ci.com/rhysmeister/AutomatingMongoDBWithAnsible)|
|Latest Build|![Build & Publish Collection](https://github.com/ansible-collections/community.mongodb/workflows/Build%20&%20Publish%20Collection/badge.svg)|

This collection called `mongodb` aims at providing all Ansible modules allowing to interact with MongoDB.
The modules present in Ansible 2.9 are included in this collection and will benefit from the evolutions and quality requirements from this collection.

As this is an independent Collection, it can be release on it's own release cadance.

## Modules

These are the modules that are available in this collection (\* = was included in ansible before 2.10):

- mongodb_balancer: Manages the MongoDB Sharded Cluster Balancer.
- mongodb_index: Creates or drops indexes on MongoDB collections.
- mongodb_info: Gather information about MongoDB instance.
- mongodb_maintenance: Enables or disables maintenance mode for a secondary member.
- mongodb_oplog: Resizes the MongoDB oplog.
- mongodb_parameter: \*Change an administrative parameter on a MongoDB server.
- mongodb_replicaset: \*Initialises a MongoDB replicaset.
- mongodb_shard: \*Add or remove shards from a MongoDB Cluster.
- mongodb_shell: Run commands via the MongoDB shell.
- mongodb_shutdown: Cleans up all database resources and then terminates the mongod/mongos process.
- mongodb_status: Validates the status of the cluster.
- mongodb_stepdown: Step down the MongoDB node from a PRIMARY state.
- mongodb_user: \*Adds or removes a user from a MongoDB database.

## Plugins

These plugins are available in this collection (\* = was included in ansible before 2.10):

- mongodb (lookup plugin): \*lookup info from MongoDB
- mongodb (cache plugin): \*Use MongoDB for caching

## Roles

These are the roles that are available in this collection:

- mongodb_linux: Configure misc linux settings recommended for MongoDB
- mongodb_selinux: Configure SELinux for MongoDB
- mongodb_repository: Add MongoDB package repository
- mongodb_install: Install MongoDB packages via mongodb-org meta-package.
- mongodb_mongod: Setup a MongoDB replicaset
- mongodb_mongos: Setup a mongos server for a MongoDB sharded cluster
- mongodb_config: Set up a CSRS Config Server Replicaset for a MongoDB sharded cluster

## Running the integration tests

Clone the collection git project. The ansible-test tool requires a specific directory setup to function correctly so please follow carefully.

```
cd && mkdir -p git/ansible_collections/community
git clone https://github.com/ansible-collections/community.mongodb.git ./ansible_collections/community/mongodb
cd ./git/ansible_collections/community/mongodb
```

Create a Python virtual environment.

```
virtualenv venv
source venv/bin/activate
pip install -r requirements-3.6.txt
```

Run integration tests for the mongodb_shard module.

```
ansible-test integration --docker default -v --color --python 3.6 mongodb_shard
```

Run integration tests for the mongodb_status module.

```
ansible-test integration --docker default -v --color --python 3.6 mongodb_status
```

Run integration tests for the mongodb_oplog module.

```
ansible-test integration --docker ubuntu1804 -v --color --python 3.6 mongodb_oplog
```

Run tests for everything in collection.

```
ansible-test integration --docker default -v --color --python 3.6
```

## GitHub workflow

* Maintainers would be members of this GitHub Repo
* Branch protections could be used to enforce 1 (or 2) reviews from relevant maintainers [CODEOWNERS](.github/CODEOWNERS)

## Contributing

Any contribution is welcome and we only ask contributors to:
* Provide *at least* integration tests for any contribution.
* Create an issues for any significant contribution that would change a large portion of the code base.

## License

GNU General Public License v3.0 or later

See LICENCING to see the full text.
