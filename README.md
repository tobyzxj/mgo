mgo
===

Mirror of [labix.org/v2/mgo](http://labix.org/mgo "Official website of mgo")

NOTE
----
You may use `import "github.com/tobyzxj/mgo"` instead of `import "labix.org/v2/mgo"`, or copy `go/src/github.com/tobyzxj/mgo` to `go/src/labix.org/v2/mgo`.

If you want to test this `mgo`, please click [gocheck](http://labix.org/gocheck "labix.org/gocheck") and [here](https://github.com/go-check/check "github.com/go-check/check")

<h2>Introduction</h2>

<p><b>mgo</b> (pronounced as <i>mango</i>) is a <a href="http://www.mongodb.org">MongoDB</a>
driver for the <a href="http://golang.org">Go language</a> that implements a
rich and well tested selection of features under a very simple API following
standard Go idioms.</p>

<p style="text-align: center;">"mgo may well be the most advanced MongoDB driver right now."<br>
&mdash; Mathias Stearn, MongoDB Engineer at 10gen</p>

<p style="text-align: center;">"mgo enables us to blazingly serve more than 1.000.000 book covers a day<br>
while reducing our servers' load."<br>
&mdash; Benoît Larroque, R&amp;D Engineer at Feedbooks.com
</p>

<p style="text-align: center;">"mgo and Go are a pair made in heaven."<br>
&mdash; Brian Ketelsen, Author of GopherTimes.com</p>

<p style="text-align: center;">"mgo is an awesome MongoDB driver, extremely fast, easy to use, and very actively maintained."<br>
&mdash; Travis Reeder, CTO of Appoxy and Iron.io</p>

<p style="text-align: center;">"mgo is the best database driver I've ever used."<br>
&mdash; Patrick Crosby, Founder of StatHat</p>

<p style="text-align: center;">"I wish there was something almost as good as mgo, but for sql."<br>
&mdash; Someone at #go-nuts</p>

<h2>Highlights</h2>

<h3>Cluster discovery and communication</h3>

<p>mgo offers automated cluster topology discovery and maintenance. Even if
provided the address to a single server in the cluster, mgo will figure out the
cluster topology and communicate with any of the servers as necessary.</p>


<h3>Failover management</h3>

<p>mgo will automatically failover in the event that the master server changes.</p>


<h3>Synchronous and concurrent</h3>

<p>mgo offers a synchronous interface, with a concurrent backend. Concurrent
operations on the same socket do not wait for the previous operation's
roundtrip before being delivered. Documents may also start being processed as
soon as the first document is received from the network, and will continue
being received in the background so that the connection is unblocked for
further requests.</p>


<h3>Result pre-fetching</h3>

<p>mgo offers configurable pre-fetching of documents, so that the next batch of
results are requested automatically when an established percentage of the
current batch has been processed.</p>


<h3>Flexible serialization</h3>

<p>mgo supports flexible marshalling and unmarshalling of documents through
gobson, a brand new BSON package written specifically to support mgo.</p>


<h3>Trivial consistency-level management</h3>

<p>mgo offers trivial consistency-level selection to tweak resource usage vs.
read/write ordering guarantees.</p>

<p>Strong consistency uses a unique connection with the master so that all
reads and writes are as up-to-date as possible and consistent with each other.</p>

<p>Monotonic consistency will start reading from a slave if possible, so that
the load is better distributed, and once the first write happens the connection
is switched to the master. This offers consistent reads and writes, but may not
show the most up-to-date data on reads which precede the first write.</p>

<p>Eventual consistency offers the best resource usage, distributing reads
across multiple slaves and writes across multiple connections to the master,
but consistency isn't guaranteed.</p>

<p>Note that this mechanism works both when connecting through a mongos server
and when connecting directly to a replica set.</p>


<h3>Authentication support with pooling integration</h3>

<p>mgo offers authentication support, with great connection pooling integration.</p>

<p>This enables mgo to talk to protected servers and replica sets in a very
comfortable way. Even with a straightforward API, the authentication is
internally cached in a secure way to avoid constant roundtrips to the database.
The use of nonces is also optimized so that logins are usually performed with a
single roundtrip to the database.</p>


<h3>GridFS support</h3>

<p>mgo can be used to send and receive files to MongoDB using the standard
GridFS specification for file storage. This means that it may share the same
database collections used for file storage with drivers for other languages,
and also the command line tools provided with MongoDB itself (e.g. mongofiles).</p>

<p>In addition to a selection of relevant methods, the *mgo.GridFile type
implements support for both io.Reader and io.Writer interfaces, which means it
integrates nicely with the standard library.</p>


<h3>Thoroughly tested</h3>

<p>Automated tests cover not only good situations, but also harsh scenarios
such as master failover.</p>


<h2>API documentation</h2>

<p>There is online documentation for both mgo, mgo/bson, and mgo/txn:</p>
<ul>
<li><a href="http://labix.org/v2/mgo">API docs for mgo</a></li>
<li><a href="http://labix.org/v2/mgo/bson">API docs for mgo/bson</a></li>
<li><a href="http://labix.org/v2/mgo/txn">API docs for mgo/txn</a></li>
</ul>


<h2>Mailing list</h2>

<p>Discussion related to the use and development of mgo is held in the
<a href="http://groups.google.com/group/mgo-users">mailing list</a>.</p>


<h2>Installing</h2>

<p>To install mgo, make sure you have the <a href="http://bazaar-vcs.org">bzr</a> command available and then run:</p>

<code>
go get labix.org/v2/mgo
</code>

<p><b>Note:</b> mgo is maintained up-to-date with the current stable
release of Go, which is Go 1 at the moment.</p>

<h2>Example</h2>

	package main
	
	import (
	        "fmt"
	        "labix.org/v2/mgo"
	        "labix.org/v2/mgo/bson"
	)
	
	type Person struct {
	        Name string
	        Phone string
	}
	
	func main() {
	        session, err := mgo.Dial("server1.example.com,server2.example.com")
	        if err != nil {
	                panic(err)
	        }
	        defer session.Close()
	
	        // Optional. Switch the session to a monotonic behavior.
	        session.SetMode(mgo.Monotonic, true)
	
	        c := session.DB("test").C("people")
	        err = c.Insert(&amp;Person{"Ale", "+55 53 8116 9639"},
		               &amp;Person{"Cla", "+55 53 8402 8510"})
	        if err != nil {
	                panic(err)
	        }
	
	        result := Person{}
	        err = c.Find(bson.M{"name": "Ale"}).One(&amp;result)
	        if err != nil {
	                panic(err)
	        }
	
	        fmt.Println("Phone:", result.Phone)
	}

<h2>License</h2>

<p>mgo is made available under the <a href="http://en.wikipedia.org/wiki/BSD_licenses#2-clause_license_.28.22Simplified_BSD_License.22_or_.22FreeBSD_License.22.29">Simplified BSD License</a>.</p>


</div>
