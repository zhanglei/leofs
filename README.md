Welcome to LeoFS
=================

Overview
--------

LeoFS is the Web shaped object storage system and S3 compatible storage.

Feature
--------

* One-Huge Storage
    * LeoFS is the Web shaped object storage system.
    * LeoFS is built to operate in highly distributed environments, such as the private cloud.
    * LeoFS has NO SPOF.
    * LeoFS's cluster consists of a set of loosely connected nodes. So, They can be viewed as ONE-Huge Storage.
    * LeoFS is made by modular-system. So, It realizes a lower cost of operations.
* 3-HIGHs
    * LeoFS is highly scalable, fault-tolerant Distributed File System for the Web.
    * Different than other DFS — LeoFS offers a number of unique benefits to users:
       * HIGH cost performance
       * HIGH Reliability
       * HIGH Scalability
* S3 Compatible
    * LeoFS is Amazon S3 compatible storage system.
    * Switch to LeoFS to decrease your cost from more expensive public-cloud solution.


Where to find more
-------------------

* Detail document is [here](http://www.leofs.org/docs/).

Quick Start
-------------

* Document is [here](http://www.leofs.org/docs/getting_started.html#quick-start)
* Prepare
  * "leofs" uses the "rebar" build system. Makefile so that simply running "make" at the top level should work.
    * [rebar](https://github.com/basho/rebar)
  * "leofs" requires [Erlang R15B03-1](http://www.erlang.org/download_release/16)
* Build and Package

```text
$ git clone https://github.com/leo-project/leofs.git
$ cd leofs
$ make
$ make release
````

* Modify Configuration File: [detail](http://www.leofs.org/docs/install.html#set-up-leofs-s-system-configuration-only-leofs-manager)
* Operate on "Manager Console": [detail](http://www.leofs.org/docs/admin_guide.html#system-operation)

```text
## Need to modify configuration files -
##     manager_master: leofs/package/leofs/manager_0/etc/app.config
##      manager_slave: leofs/package/leofs/manager_1/etc/app.config
##            storage: leofs/package/leofs/storage/etc/app.config
##            gateway: leofs/package/leofs/storage/etc/app.config

$ cd package/leofs
$ manager_0/bin/leo_manager start
$ manager_1/bin/leo_manager start
$ storage/bin/leo_storage start

## Need to operate on "LeoFS-Manager's Console" -
##     - Command: [START, STATUS]

$ gateway/bin/leo_gateway start

## Confirm LeoFS's Status on "LeoFS-Manager's Console" -
##     - Command: [STATUS]
````

* Clients
    * Connect LeoFS from [DragonDisk](http://www.dragondisk.com/)
    * Connect LeoFS from [Client of Program Language](http://www.leofs.org/docs/s3_client.html)
    * Connect LeoFS from [S3FS-C](http://www.leofs.org/docs/s3_client.html#getting-started-with-s3fs-c-ubuntu-12-04-lts)


GOALs
-------
* LeoFS aims to provide the following advantages:
  * HIGH Cost Performance
     * Fast - Over 200MB/sec into 10GE (READ)
     * A lower cost than other storage
     * Provide easy management and easy operation
  * HIGH Reliability
     * Nine nines - Operating ratios is 99.9999999%
  * High Scalability
     * Build Huge-Cluster at low cost

Milestones
-----------

* *DONE* - 0.12 (Oct 2012 - Jan 2013)
    * Large Object Support (incl.Streaming/Multi-part/Range requests)
    * Web GUI-Console (LeoTamer - Optional)
        * Cluster manager/monitor
        * Log Analysis/Search
* *DONE* - 0.14 (Feb 2013 - Sep)
    * Multi-layer Cache (Using SSD)
    * Rack aware replica placement
    * Web GUI Console (Option)
       * Support whole LeoFS Manager's commands
* 0.16 (Oct 2013)
    * Increase compatibility S3-APIs#4
        * the bucket ACLs
    * Web GUI Console (Option)
       * Support whole LeoFS Manager's commands
* 1.0 (Nov 2013 - Dec)
    * Multi Data Center Replication
    * Increase compatibility S3-APIs#5
        * Other bucket operations
    * QoS System Phase-1 (LeoInsight - Option)
       * Support *statistics/analyzer*
* 1.2 (Jan 2014 - Apr)
    * OpenStack Integration
        * Support for OpenStack Swift-API
    * Increase compatibility S3-APIs#6
        * Objects Expiration into the bucket
        * Versioning
    * Job Scheduler on the Manager
        * Support *auto-compaction*
    * QoS System Phase-2 (LeoInsight - Option)
       * Support *notifier*
    * Web GUI Console (Option)
        * LeoInsight(QoS) Integration
        * Support Log analysis/search
