bzr log:
=======

------------------------------------------------------------
revno: 286
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-06-30 21:04:13 -0300
message:
  Add GridFile.Abort and remove chunks on any error at Close.
------------------------------------------------------------
revno: 285
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-06-30 20:42:58 -0300
message:
  Drop unnecessary early optimization.
------------------------------------------------------------
revno: 284
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2014-06-24 15:13:39 -0300
message:
  Confirm GetBSON nil handling behavior with test.
------------------------------------------------------------
revno: 283
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-06-23 12:43:59 -0300
message:
  Make SimpleQuery race safe, irrespective of what the server does.
------------------------------------------------------------
revno: 282
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-06-21 14:27:54 -0300
message:
  Support for PLAIN (LDAP) authentication.
------------------------------------------------------------
revno: 281
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2014-06-20 20:01:53 -0300
message:
  Preliminary support for Bulk API.
  
  In addition to preparing for the full blown bulk API, this
  adds support for the ContinueOnError flag of the insert
  operation in a way that will remain compatible with the
  upcoming bulk operation commands.
  
  The latter feature was requested by Chandra Sekar.
------------------------------------------------------------
revno: 280
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-06-18 18:51:24 -0300
message:
  Handle another test-only race.
------------------------------------------------------------
revno: 279
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-06-18 17:17:57 -0300
message:
  Silence race detector on racy logging setup logic.
------------------------------------------------------------
revno: 278
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-06-18 17:16:22 -0300
message:
  Stabilize test suite avoiding timing checks.
------------------------------------------------------------
revno: 277
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-06-18 14:56:09 -0300
message:
  Wake up nonce waiters on socket death.
  
  Thanks to John Morales for the report and diagnosis.
------------------------------------------------------------
revno: 276
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2014-06-17 14:15:26 -0300
message:
  Old user methods are now compatible with 2.6+.
------------------------------------------------------------
revno: 275
tags: go1
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2014-05-01 11:46:51 -0700
message:
  Don't burn CPU if no masters are found and FailFast is set.
              
  Reported by John Morales.
------------------------------------------------------------
revno: 274
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2014-04-08 23:57:44 -0300
message:
  Tweak tests for 2.6.
------------------------------------------------------------
revno: 273
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-03-31 15:50:09 -0300
message:
  Break out of Iter.Next if getMore failed.
  
  Problem reported by Daniel Gottlieb.
------------------------------------------------------------
revno: 272
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-03-24 19:45:48 -0300
message:
  Small comment fixes, by Dmitry Chestnykh.
------------------------------------------------------------
revno: 271
tags: r2014.03.12
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 20:06:39 -0300
message:
  Trivial tweaks in package-level docs.
------------------------------------------------------------
revno: 270
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 20:02:16 -0300
message:
  Get rid of "against" in the documentation. What a bad word.
------------------------------------------------------------
revno: 269
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 19:57:35 -0300
message:
  In public docs: master => primary; slave => secondary
------------------------------------------------------------
revno: 268
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 19:53:39 -0300
message:
  Document new Dial options.
------------------------------------------------------------
revno: 267
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 19:53:28 -0300
message:
  Lowercase errors and panics.
------------------------------------------------------------
revno: 266
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 02:15:58 -0300
message:
  Experimental SASL support.
------------------------------------------------------------
revno: 265
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 02:15:20 -0300
message:
  Prevent calling reply func twice on killed sockets.
  
  There was a small chance that the reply handling function might
  be called twice when a socket was killed during the reply
  handling phase.
  
  Problem first reported at LP #1225196 by Francisco Souza and
  then as MGO-21 by John Morales.
------------------------------------------------------------
revno: 264
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2014-03-12 02:13:45 -0300
message:
  Clean up login logic.
------------------------------------------------------------
revno: 263
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 22:01:27 -0200
message:
  Assign socket.dead to local variable so the race detector doesn't see
  a potential race. Note that there's no *actual* race, since socket.dead
  is always tested while locked, and once it's set once, it never changes.
  
  Reported by Evan Shaw.
------------------------------------------------------------
revno: 262
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 21:56:58 -0200
message:
  Unlock iter.m on a missing exit path of Iter.Next.
  
  Problem reported by Evan Shaw.
------------------------------------------------------------
revno: 261
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 21:50:43 -0200
message:
  Lock iter when changing iter.err due to potential races with replyFunc.
  
  Problem reported by Evan Shaw.
------------------------------------------------------------
revno: 260
tags: r2014.01.25
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 16:14:51 -0200
message:
  Removed "experimental" note from DialServer, and obsoleted Dial.
------------------------------------------------------------
revno: 259
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 15:54:08 -0200
message:
  Fixed value of the RoleUserAdminAny string constant. Problem
  reported by Serhat Sevki Dincer.
------------------------------------------------------------
revno: 258
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 15:51:05 -0200
message:
  Improve IsDup so it handles duplication errors with code 16460,
  which happen on sharded environments. This is also being fixed
  upstream in MongoDB, as reported in bug SERVER-11493.
  
  Problem reported by Feng Liyuan.
------------------------------------------------------------
revno: 257
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sat 2014-01-25 15:41:22 -0200
message:
  Introduced FailFast option in DialInfo.
  
  FailFast will cause connection and query attempts to fail faster when
  the server is unavailable, instead of retrying until the configured
  timeout period. Note that an unavailable server may silently drop
  packets instead of rejecting them, in which case it's impossible to
  distinguish it from a slow server, so the timeout stays relevant.
  
  Feature requested by Louisa Berger and Cailin Nelson.
------------------------------------------------------------
revno: 256
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2014-01-23 23:06:51 -0200
message:
  Increase number of elements in MapReduceVerbose test to stabilize it.
------------------------------------------------------------
revno: 255
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2014-01-23 23:03:55 -0200
message:
  Tweaked documentation and parameter names to avoid confusion between the
  update document some methods take, and values of the mgo.Change type.
------------------------------------------------------------
revno: 254
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2014-01-20 20:24:05 -0200
message:
  Added Runner.PurgeMissing on txn package.
------------------------------------------------------------
revno: 253
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2013-12-10 20:41:42 -0200
message:
  Experimental DialServer field in DialInfo struct.
------------------------------------------------------------
revno: 252
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2013-11-19 21:24:18 -0200
message:
  Session.SetCursorTimeout is the new Query.DisableCursorTimeout.
------------------------------------------------------------
revno: 251
tags: r2013.11.18
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-11-18 20:48:22 -0200
message:
  Document that Query.Apply depends on MongoDB >= 2.0.
------------------------------------------------------------
revno: 250
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-11-18 20:17:17 -0200
message:
  Add support for maps with custom string key types.
  
  Feature requested by Emre Kazdagli.
------------------------------------------------------------
revno: 249
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-11-18 20:00:39 -0200
message:
  Add Query.DisableCursorTimeout.
  
  Feature requested by Ali Sufian.
------------------------------------------------------------
revno: 248
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-11-18 19:37:20 -0200
message:
  Handle elements with custom slices of bson.Raw.
  
  Problem reported by Daniel Gottlieb.
------------------------------------------------------------
revno: 247 [merge]
author: Michael Hudson-Doyle <michael.hudson+lp@canonical.com>
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: v2
timestamp: Wed 2013-11-13 11:30:59 -0200
message:
  bson: don't trust expression evaluation order
  
  The evaluation order of
  
    end := d.i - 4 + int(d.readInt32())
  
  differs when compiled with gccgo vs the gc toolchain, and is
  apparently unspecified according to the spec.
------------------------------------------------------------
revno: 246
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-09-08 12:30:45 -0300
message:
  mgo/bson: add package-level documentation
------------------------------------------------------------
revno: 245
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-09-06 13:20:00 -0300
message:
  Fix socket timeout logic for innactive sockets.
  
  Problem reported by Rangel Reale.
------------------------------------------------------------
revno: 244
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-09-06 11:27:33 -0300
message:
  Increase the socket timeout used by the pinger.
------------------------------------------------------------
revno: 243
tags: r2013.09.04
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2013-09-05 14:53:08 -0300
message:
  Fixed omitempty for non-comparable structs.
  
  Problem reported by Andrew Bonventre.
------------------------------------------------------------
revno: 242
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2013-09-03 23:25:56 -0300
message:
  The "out" option in the MapReduce command must be ordered. This was
  found after the implementation was accepting maps for a long time,
  so rather than breaking the API, the implementation will fix the
  order if necessary.
  
  Details about the order requirement may be seen in MongoDB's code:
  
      http://goo.gl/L8jwJX
  
  Thanks to Peter Kleiweg for reporting the issue.
------------------------------------------------------------
revno: 241
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Tue 2013-09-03 22:38:56 -0300
message:
  Improved timeout support to include socket-level deadlines.
------------------------------------------------------------
revno: 240
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-08-30 16:40:15 -0300
message:
  bson: support omitempty in struct value fields
------------------------------------------------------------
revno: 239
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-08-30 15:32:22 -0300
message:
  txn: fix transactions with multiple ops on same document
  
  The application of multiple operations on the same document id in the
  same transaction was not functioning properly. All but the first
  transaction would fail to apply due to miscalculation of the sequence
  of revnos.
  
  So, for example, if a a transaction was doing Insert+Update on the
  same collection and id, the Update was never applied, whether the
  document existed or not. If the transaction was doing Update+Insert,
  the Update is currently applied if the document exists, and
  the Insert is never applied.
  
  This change fixes that. Insert+Update will now work properly if the
  document exists or not (if it exists only the Update will do something).
  Doing Update+Insert is a nice to way to say "either update or insert",
  as only a single one of them can possibly work depending on whether
  the document exists or not.
  
  This change should not affect existent code, unless the code was
  already buggy and not functioning properly.
------------------------------------------------------------
revno: 238
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-08-04 20:00:08 -0300
message:
  bson: added RawD and RawDocElem support
------------------------------------------------------------
revno: 237
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-22 13:42:45 -0300
message:
  file.Close => (*file).Close, to make Roger's implements tool happy.
------------------------------------------------------------
revno: 236
tags: r2013.07.21
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-22 01:12:49 -0300
message:
  Polish the suite a tad.
------------------------------------------------------------
revno: 235
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-22 01:12:34 -0300
message:
  Do not panic on ancient binary format that has no length as part of the
  binary data (doesn't seem to follow the spec). Issue reported by
  Daniel Gottlieb.
------------------------------------------------------------
revno: 234
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-07-21 17:02:01 -0300
message:
  Allow Login command to run against secondaries. This fixes support for
  authorization done after a direct connection is established against a
  secondary. Problem discovered and debugged by Bard Bloom.
------------------------------------------------------------
revno: 233
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-07-21 14:39:51 -0300
message:
  Encode int as int64 when the compiler supports 64 bits ints and the
  int is over range.
------------------------------------------------------------
revno: 232
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-07-21 14:38:26 -0300
message:
  Implemented SelectServers.
------------------------------------------------------------
revno: 231
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-15 21:25:40 -0300
message:
  Started support for server tags.
------------------------------------------------------------
revno: 230
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-15 20:16:48 -0300
message:
  Fix nearest secondary selection so that it doesn't fallback to
  number of sockets if the either of the servers being considered 
  are away by more than 15ms.
------------------------------------------------------------
revno: 229
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-07-15 20:10:44 -0300
message:
  Fix missing constant in test.
------------------------------------------------------------
revno: 228
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2013-06-20 09:00:45 -0400
message:
  Fix the previous fix by releasing the socket before closing it.
  
  Also add a simple concurrency test to verify both the
  original bug and the new one.
------------------------------------------------------------
revno: 227 [merge]
author: John A Meinel <john@arbash-meinel.com>
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: v2
timestamp: Tue 2013-06-18 10:40:27 -0400
message:
  Fix race in AcquireSocket
  
  Fix AcquireSocket so it doesn't put sockets in the live list after
  the server has been closed. Fix by John Meinel.
  
  R=rog, niemeyer
  CC=
  https://codereview.appspot.com/10392043
------------------------------------------------------------
revno: 226
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-06-17 15:53:49 -0300
message:
  Add number of clusters alive to statistics, and add leak check to suite.
------------------------------------------------------------
revno: 225
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-06-17 10:37:37 -0300
message:
  go fmt
------------------------------------------------------------
revno: 224
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-06-16 21:20:01 -0300
message:
  Read correctly index documents defined with floats.
  
  That's what generally ends up in them, whenever the shell is used
  to define the index. Bug reported by Nick Stott.
  
  Also fix the index names to include the kind. It uses to not include
  the name because the shell had a bug, and mgo preserved the same bug,
  but now that the shell is fixed there's no reason to keep the broken
  behavior.
------------------------------------------------------------
revno: 223
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-06-09 20:52:38 -0300
message:
  Allow slave writes on the "local" database.
------------------------------------------------------------
revno: 222
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-05-31 18:44:07 -0300
message:
  Send pings with op.limit = -1; mongos blows up without it.
  
  Thanks to Evan Shaw for the note.
------------------------------------------------------------
revno: 221
tags: r2013.05.19
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Sun 2013-05-19 18:31:48 -0300
message:
  - New cluster synchronization logic reuses existing connections.
  - Introduced nearest slave server detection.
  - Sleep a bit when retrying an individual server during synchronization
    due to socket errors, to avoid punching the system needlessly.
------------------------------------------------------------
revno: 220
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Mon 2013-04-15 20:54:36 -0300
message:
  Clarify that the Runner.Run applies operations in order in the
  txn package, as suggested by Roger. 
------------------------------------------------------------
revno: 219
tags: r2013.04.11
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2013-04-11 03:18:48 -0300
message:
  Document inlining of maps, and error out if inlined map keys conflict
  with struct fields when encoding.
------------------------------------------------------------
revno: 218
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Thu 2013-04-11 02:27:36 -0300
message:
  Handle properly quick primary hiccups that just shift away
  primary status.
------------------------------------------------------------
revno: 217
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2013-04-10 21:25:01 -0300
message:
  Add session test to ensure inline maps work for real.
------------------------------------------------------------
revno: 216
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2013-04-10 21:12:35 -0300
message:
  Introduced the concept of inline maps.
------------------------------------------------------------
revno: 215
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Wed 2013-04-10 21:12:06 -0300
message:
  Minor tweak in suite test.
------------------------------------------------------------
revno: 214 [merge]
tags: r2013.04.05
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-04-05 19:48:08 -0300
message:
  Merged bson.NewObjectId concurrency fix from tip.
------------------------------------------------------------
revno: 213
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-04-05 18:16:41 -0300
message:
  Revert test hack committed by mistake.
------------------------------------------------------------
revno: 212
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-04-05 18:15:11 -0300
message:
  Add UpsertUser method.
------------------------------------------------------------
revno: 211
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: master
timestamp: Fri 2013-04-05 14:00:16 -0300
message:
  Fix concurrency issue on acquireSocket.
------------------------------------------------------------
revno: 210
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-04-01 19:34:54 -0300
message:
  Improve IsDup so it handles more cases. It's sad that this is necessary.
------------------------------------------------------------
revno: 209
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-04-01 18:10:19 -0300
message:
  Add Query.LogReplay method.
------------------------------------------------------------
revno: 208
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-04-01 18:10:01 -0300
message:
  Missed the v3 => v2 transition inside txn/.
------------------------------------------------------------
revno: 207
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 08:06:44 -0300
message:
  Fix test handling of iter.Close vs. iter.Err.
------------------------------------------------------------
revno: 206
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 07:31:48 -0300
message:
  v3 => v2. Woohay backwards compatibility.
------------------------------------------------------------
revno: 205
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 07:30:39 -0300
message:
  Drop mgofix. We'll need it someday, but it's in the history.
------------------------------------------------------------
revno: 204
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 07:30:05 -0300
message:
  Revive For methods.
  
  This re-establishes compatibility with v2.
------------------------------------------------------------
revno: 203
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 07:20:03 -0300
message:
  Clarify documentation of GridFS.Open* methods to mention these
  files are to be read from, only.
------------------------------------------------------------
revno: 202
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 07:13:58 -0300
message:
  - Revive iter.Err. We probably don't need a v3 right now.
  - Drop SetFinalizer on session. GC didn't work well on iter,
    don't risk on session.
  - Improve documentation on Close.
------------------------------------------------------------
revno: 201
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2013-03-30 05:47:09 -0300
message:
  Added test to ensure authentication works on sharded setups,
  including when primary falls down.
------------------------------------------------------------
revno: 200
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2013-03-27 09:46:45 -0300
message:
  Added authenticated shard cluster to the test suite.
------------------------------------------------------------
revno: 199
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2013-03-27 01:19:51 -0300
message:
  Added migration tool from v2 to v3.
------------------------------------------------------------
revno: 198
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 23:21:21 -0300
message:
  Kill the cursor on Iter.Close, if necessary.
------------------------------------------------------------
revno: 197
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 23:01:13 -0300
message:
  Upgrade import paths to v3.
------------------------------------------------------------
revno: 196
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 21:44:35 -0300
message:
  - Iter.Err is now Iter.Close
  - Dropped obsolete For methods.
------------------------------------------------------------
revno: 195
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 21:33:51 -0300
message:
  Other minor test fixes for 2.4.
------------------------------------------------------------
revno: 194
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 19:33:15 -0300
message:
  auth_test.go: fix expected auth error messages for 2.4
------------------------------------------------------------
revno: 193
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-03-26 19:10:32 -0300
message:
  supervisord.conf: drop startsecs for mongos
------------------------------------------------------------
revno: 192
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2013-02-27 00:24:37 -0300
message:
  Test direct connection to a replicaset server in unknown membership state.
------------------------------------------------------------
revno: 191
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2013-02-26 23:20:30 -0300
message:
  Allow direct connection to replica set member in unknown state.
------------------------------------------------------------
revno: 190
tags: r2013.01.20
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-01-21 01:12:24 -0200
message:
  Fixed omitempty on float values, as reported by Otto Bretz.
------------------------------------------------------------
revno: 189
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-01-21 01:06:38 -0200
message:
  New bson.IsObjectIdHex function.
------------------------------------------------------------
revno: 188
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2013-01-21 00:38:03 -0200
message:
  In preparation for 2.4, which is coming with multiple new index types,
  change the format of 2D indexes from "@foo" to "$2d:foo". Preserve
  parsing of the old style for compatibility.
------------------------------------------------------------
revno: 187
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2013-01-20 23:32:01 -0200
message:
  Fix DialWithInfo so it dials to the standard MongoDB port if the address
  doesn't inform one. Thanks to Mark Severson for reporting the issue.
------------------------------------------------------------
revno: 186
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2013-01-20 22:42:47 -0200
message:
  Add note the Write method on GridFS explaining that errors may
  be delayed until a future Write or Close, as suggested by
  Ian Ragsdale.
------------------------------------------------------------
revno: 185
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2013-01-20 22:33:10 -0200
message:
  Fixed typo in code in docs. Contributed by Livio Soares.
------------------------------------------------------------
revno: 184
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2013-01-20 22:28:59 -0200
message:
  Ensure open cursor is killed before finishing an iterator with limit.
  Issue reported by Andrew Bonventre.
------------------------------------------------------------
revno: 183
tags: r2012.10.28
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-28 16:49:41 +0100
message:
  Introduced ability to provide custom Dial functions.
------------------------------------------------------------
revno: 182
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-28 12:51:42 +0100
message:
  Introduced DialInfo type and DialWithInfo function containing the
  actual dialing logic, and moved the logic from other Dial functions
  into it.
------------------------------------------------------------
revno: 181
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-28 11:32:13 +0100
message:
  Reset non-nil interfaces. That case actually happens in practice.
  Bug reported by Peter Kleiweg.
------------------------------------------------------------
revno: 180
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-28 11:10:18 +0100
message:
  Ensure the same server is used during iteration.
  This fixes long iterations on Eventual sessions.
------------------------------------------------------------
revno: 179
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-14 23:03:10 -0300
message:
  Fixed behavior of limit.
------------------------------------------------------------
revno: 178
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-10-14 19:32:11 -0300
message:
  Workaround bug in OpenShift that prevents hostname from being retrieved.
------------------------------------------------------------
revno: 177
tags: r2012.10.04
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-10-05 00:20:18 -0300
message:
  Server closes cursor when batch is 1. Use 2 instead.
------------------------------------------------------------
revno: 176
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-10-04 23:55:01 -0300
message:
  Preserve slave socket with session on Monotonic so that
  iterations don't break down when writes happen inside the
  iteration, forcing a shift to the master.
------------------------------------------------------------
revno: 175
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-09-26 12:37:31 -0300
message:
  Use IsDup when inserting document into changelog to make sure
  it works with capped collections as well.
------------------------------------------------------------
revno: 174
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-09-26 11:38:55 -0300
message:
  Greatly reduce the space needed to start the test servers by
  using --oplogSize.
------------------------------------------------------------
revno: 173
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-09-26 11:37:26 -0300
message:
  Added IsDup error checker for convenience and to workaround the
  fact capped collections and normal collections have different
  errors for conflicting keys. Reported upstream as:
  
      https://jira.mongodb.org/browse/SERVER-7164
------------------------------------------------------------
revno: 172
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-09-17 09:32:12 -0300
message:
  Added SetZero support.
------------------------------------------------------------
revno: 171
tags: r2012.09.05
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-09-05 09:34:00 -0300
message:
  Introduced support for TTL collections.
------------------------------------------------------------
revno: 170
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-09-05 08:29:42 -0300
message:
  Added Pipe method supporting the aggregation framework.
------------------------------------------------------------
revno: 169
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-08-28 00:12:51 -0300
message:
  Added change log support.
------------------------------------------------------------
revno: 168
tags: r2012.08.23
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 22:12:06 -0300
message:
  Fixed tests after bson fixes.
------------------------------------------------------------
revno: 167
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 22:11:54 -0300
message:
  Fixed ordering of fields.
------------------------------------------------------------
revno: 166
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 21:48:36 -0300
message:
  Added field ordering test.
------------------------------------------------------------
revno: 165
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 20:31:47 -0300
message:
  Properly decode custom generic map and slices, even
  nested ones.
------------------------------------------------------------
revno: 164
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 10:20:55 -0300
message:
  Allow custom bson.D-like types.
------------------------------------------------------------
revno: 163
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 09:56:26 -0300
message:
  Operation => Op, DocId => Id, Collection => C.
------------------------------------------------------------
revno: 162
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 09:36:18 -0300
message:
  Fixed bug after field renames.
------------------------------------------------------------
revno: 161
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 08:36:28 -0300
message:
  Validate operations before writing the transaction.
------------------------------------------------------------
revno: 160
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 07:39:39 -0300
message:
  Optimized field names, types, and tags.
------------------------------------------------------------
revno: 159
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 07:24:42 -0300
message:
  Added support for default database via DB("").
------------------------------------------------------------
revno: 158
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-08-23 05:51:10 -0300
message:
  Trivial cleanups.
------------------------------------------------------------
revno: 157
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 19:03:31 -0300
message:
  Fix Chaos docs.
------------------------------------------------------------
revno: 156
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 19:00:28 -0300
message:
  Actually implement Info support.
------------------------------------------------------------
revno: 155
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 18:51:23 -0300
message:
  Renamed Change field to Update.
------------------------------------------------------------
revno: 154
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 17:34:47 -0300
message:
  Fixed typo.
------------------------------------------------------------
revno: 153
tags: r2012.08.22
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 16:53:39 -0300
message:
  Dropped support for fake runner.
------------------------------------------------------------
revno: 152
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 16:38:53 -0300
message:
  Fixed txn blog post URL.
------------------------------------------------------------
revno: 151
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 15:47:39 -0300
message:
  Trivial doc tweaks.
------------------------------------------------------------
revno: 150
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-08-22 09:23:19 -0300
message:
  Moving txn into the main repo.
------------------------------------------------------------
revno: 149
tags: r2012.08.07
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-08-07 00:37:36 +0100
message:
  Ensure Apply always goes to the master.
------------------------------------------------------------
revno: 148
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-08-07 00:16:16 +0100
message:
  Fixed socket leak that might happen when a primary stepped down
  and stayed in a state when it was neither a primary nor a
  secondary.
------------------------------------------------------------
revno: 147
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-08-06 23:32:29 +0100
message:
  All session tests passing.
------------------------------------------------------------
revno: 146
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-07-30 00:30:40 -0300
message:
  Fix BuildInfo test for rc release.
------------------------------------------------------------
revno: 145
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-07-30 00:20:54 -0300
message:
  Fixed authorization issues with 2.2.
------------------------------------------------------------
revno: 144
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-07-28 15:56:58 -0300
message:
  Add UpdateId, UpsertId, and RemoveId.
------------------------------------------------------------
revno: 143
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-07-28 15:05:50 -0300
message:
  Don't call Now on fast path of Next.
------------------------------------------------------------
revno: 142
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-07-28 14:36:07 -0300
message:
  Polished prefetching edges further. Better testing.
------------------------------------------------------------
revno: 141
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-07-28 10:37:21 +0100
message:
  Fixed pre-fetching to avoid gradually loading more documents
  than consumed, thus increasing memory use during iteration.
------------------------------------------------------------
revno: 140
tags: r2012.06.22
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-06-22 17:01:34 -0300
message:
  Use labix.org import paths.
------------------------------------------------------------
revno: 139
tags: go.weekly.2012-01-20
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-06-22 03:08:15 -0300
message:
  Change string for ErrNotFound.
------------------------------------------------------------
revno: 138
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-06-22 02:55:12 -0300
message:
  FindRef now returns a *Query.
------------------------------------------------------------
revno: 137
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-06-22 02:28:20 -0300
message:
  Significant breaking changes to introduce *ChangeInfo.
  
  Also cleaned up other pending incompatibilities at the same time.
------------------------------------------------------------
revno: 136
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-06-21 22:55:25 -0300
message:
  Added links to MongoDB docs on collection creation.
------------------------------------------------------------
revno: 135
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-06-21 22:53:56 -0300
message:
  Added Collection.Create method.
------------------------------------------------------------
revno: 134
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-06-21 22:08:55 -0300
message:
  Simplified parameters for EnsureIndexKey, DropIndex, and Hint.
------------------------------------------------------------
revno: 133
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-06-21 21:29:03 -0300
message:
  Take time.Now out of the fast path for obtaining a socket to
  run queries. Reported by Felix Sun.
------------------------------------------------------------
revno: 132
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-06-21 20:45:02 -0300
message:
  Added FindId helper.
------------------------------------------------------------
revno: 131
tags: r2012.05.21
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-05-21 01:23:43 -0300
message:
  Find(q).One(nil) was mishandling errors.
------------------------------------------------------------
revno: 130
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-05-21 00:58:09 -0300
message:
  Further mongod flags to speed up tests.
------------------------------------------------------------
revno: 129
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-05-15 22:09:23 -0300
message:
  Unpack lastErrorObject on findAndModify command errors.
  
  Thanks to Evan Shaw for the bug report.
------------------------------------------------------------
revno: 128
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-04-16 20:36:57 -0300
message:
  Improve resilience to random server faults.
------------------------------------------------------------
revno: 127
tags: r2012.04.08
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-04-08 17:21:03 -0300
message:
  Added Fsync, FsyncLock, and FsyncUnlock to Session.
------------------------------------------------------------
revno: 126
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-04-08 08:53:47 -0300
message:
  Speed up checkQueryError. Fixes 969490.
------------------------------------------------------------
revno: 125
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-04-07 20:11:46 -0300
message:
  Simplified Sort arguments.
------------------------------------------------------------
revno: 124
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-04-07 19:08:13 -0300
message:
  Added Query.Snapshot. Fixes 954416.
------------------------------------------------------------
revno: 123
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-04-07 16:40:26 -0300
message:
  URL parsing must split options at both & and ;
------------------------------------------------------------
revno: 122
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-04-07 16:22:56 -0300
message:
  bson: fix overflowing in time.Time handling
------------------------------------------------------------
revno: 121
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-04-07 15:52:17 -0300
message:
  bson: support omitempty on time.Time.
  
  Fixes issue 976131.
------------------------------------------------------------
revno: 120
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Wed 2012-04-04 00:41:24 -0300
message:
  Hard per-server socket limit is now 4096.
------------------------------------------------------------
revno: 119
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-04-03 01:32:31 -0300
message:
  - Balance usage of servers based on the number of sockets
    in use rather than on a random selection.
  - There's now a top limit for the number of connections
    established against a single server. This is set to 512,
    to begin with. This is backfire protection, rather than
    something people should be trusting on.
------------------------------------------------------------
revno: 118
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-04-02 19:22:57 -0300
message:
  Some additional internal method comments.
------------------------------------------------------------
revno: 117
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-03-30 18:49:29 -0300
message:
  Fix edge case with Limit(MinInt32), again pointed out by Jeff Wendling.
------------------------------------------------------------
revno: 116
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Fri 2012-03-30 18:02:38 -0300
message:
  Fix handling of Limit with large volume of data. When Limit was used,
  the cursor was improperly being terminated after the first chunk of
  data, that amounts to about 4MB by default. Thanks to Jeff Wendling
  for reporting the problem and providing a nice reproducer.
------------------------------------------------------------
revno: 115
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-03-26 14:54:06 -0300
message:
  s/os.Error/error/ in example. Thanks to Agon on IRC.
------------------------------------------------------------
revno: 114
tags: r2012.03.04
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-03-04 11:55:44 -0300
message:
  Clarified documentation of EnsureIndex's Background field.
------------------------------------------------------------
revno: 113
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-03-04 10:48:41 -0300
message:
  Fix unmarshaling of arrays, reported by John Asmuth.
------------------------------------------------------------
revno: 112
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-03-04 09:59:57 -0300
message:
  Added support for url.URL marshaling.
------------------------------------------------------------
revno: 111
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-03-04 09:07:58 -0300
message:
  Added support for ignoring fields with "-".
------------------------------------------------------------
revno: 110
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-03-04 08:48:33 -0300
message:
  Ported to new gocheck.
------------------------------------------------------------
revno: 109
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-02-09 19:19:10 -0200
message:
  Fixed documentation referring to mgo.Mongo.
------------------------------------------------------------
revno: 108
tags: r2012.02.02
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-02-02 20:39:12 -0200
message:
  Minor doc update.
------------------------------------------------------------
revno: 107
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-02-02 19:59:13 -0200
message:
  Getter.GetBSON method may now return an error.
------------------------------------------------------------
revno: 106
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Thu 2012-02-02 09:42:51 -0200
message:
  Improve synchronization further.
------------------------------------------------------------
revno: 105
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Tue 2012-01-31 07:41:09 -0200
message:
  Improvements in cluster synchronization logic.
------------------------------------------------------------
revno: 104
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-29 22:12:08 -0200
message:
  Further improved the cluster removal test, plus minor
  documentation tweak.
------------------------------------------------------------
revno: 103
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-29 21:21:22 -0200
message:
  Minor docstring improvement.
------------------------------------------------------------
revno: 102
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-29 21:21:18 -0200
message:
  Improved cluster member removal test.
------------------------------------------------------------
revno: 101
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-29 19:15:24 -0200
message:
  Removed bson.Timestamp and add support for time.Time.
------------------------------------------------------------
revno: 100
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-01-28 12:10:04 -0200
message:
  - NewObjectIdSeconds was renamed NewObjectIdWithTime, and now takes
    a time.Time as argument
  - The ObjectId.Timestamp method was renamed ObjectId.Time and now
    returns a time.Time.
------------------------------------------------------------
revno: 99
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-01-28 11:10:40 -0200
message:
  - gobson*.go renamed bson*.go.
  - Removed makefile-based building.
------------------------------------------------------------
revno: 98
tags: r2012.01.22
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Mon 2012-01-23 00:01:51 -0200
message:
  New interface for DBRef.
------------------------------------------------------------
revno: 97
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 23:53:17 -0200
message:
  - Increased follow up timeout of Dial to one minute.
  - New disabled test towards verifying that replica set member
    removals are correctly processed.
------------------------------------------------------------
revno: 96
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 20:31:55 -0200
message:
  Fixed unsafe concurrent access to data detected
  by Dmitry Vyukov with ThreadSanitizer.
------------------------------------------------------------
revno: 95
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 20:16:03 -0200
message:
  - Database, Collection, and GridFS are handled as pointers everywhere.
  - New Database.With and Collection.With methods to replace the session
    they're linked with.
------------------------------------------------------------
revno: 94
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 18:19:46 -0200
message:
  Renamed Get/SetInfo to Get/SetMeta.
------------------------------------------------------------
revno: 93
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 12:20:05 -0200
message:
  Added GridFS.Find helper.
------------------------------------------------------------
revno: 92
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 12:09:14 -0200
message:
  Implemented GridFS.OpenNext.
------------------------------------------------------------
revno: 91
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sun 2012-01-22 00:39:04 -0200
message:
  - Replaced Mongo by the improved Dial and DialWithTimeout functions.
  - Use time.Duration on SetSyncTimeout and Tail.
------------------------------------------------------------
revno: 90
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-01-21 19:08:11 -0200
message:
  Renamed Mongo function to Dial.
------------------------------------------------------------
revno: 89
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: mgo
timestamp: Sat 2012-01-21 18:44:10 -0200
message:
  - Imported bson package onto bson/.
  - Fixed license to simplified BSD.
------------------------------------------------------------
revno: 88 [merge]
tags: r2011.12.18.weekly, go.weekly.2011-12-14
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-12-18 17:15:06 -0200
message:
  Merged back changes supporting latest weekly.
------------------------------------------------------------
revno: 87
tags: r2011.12.18, go.r60
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: go-r60-maint
timestamp: Wed 2011-12-14 06:57:07 -0200
message:
  Fix Count so it takes Limit and Skip in consideration, as
  reported by Paddy Foran.
------------------------------------------------------------
revno: 86
tags: r2011.10.29
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-10-29 12:38:54 -0400
message:
  Renamed receiver variables to make docs nicer.
------------------------------------------------------------
revno: 85
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-10-25 20:27:41 -0400
message:
  - Brand new iteraction interface!
  - New Iter.All and Query.All methods.
  - Fixed Update and UpdateAll with nil selector.
  - Obsoleted Iter.For and Query.For
------------------------------------------------------------
revno: 84
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-10-19 19:05:05 -0200
message:
  Improve the test suite a bit.
------------------------------------------------------------
revno: 83
tags: r2011.09.15
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-09-15 00:32:02 -0300
message:
  CollectionNames had a pointer receiver.
------------------------------------------------------------
revno: 82
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-09-14 23:56:50 -0300
message:
  Added DropCollection and DropDatabase.
------------------------------------------------------------
revno: 81
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-09-14 23:05:52 -0300
message:
  Assemble VersionArray if not provided by server.
------------------------------------------------------------
revno: 80
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-09-14 22:39:03 -0300
message:
  Added support for WMode and J in Safe.
------------------------------------------------------------
revno: 79
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-09-14 20:49:39 -0300
message:
  Implemented support for BuildInfo.
------------------------------------------------------------
revno: 78
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-09-14 19:37:44 -0300
message:
  Fixed compatibility with Mongo 2.0.0.
------------------------------------------------------------
revno: 77
tags: go.2011-08-17, go.r59, r2011.08.21
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-08-20 18:55:11 -0300
message:
  Implemented GridFile.Seek
------------------------------------------------------------
revno: 76
tags: r2011.08.02
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-08-02 21:53:38 -0300
message:
  Implemented GridFile.UploadDate.
------------------------------------------------------------
revno: 75
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-08-02 20:31:15 -0300
message:
  Use long flag names.
------------------------------------------------------------
revno: 74
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-08-02 00:12:13 -0300
message:
  s/GetRef/FindRef/ & s/GetLiveServers/LiveServers/g
------------------------------------------------------------
revno: 73
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-08-02 00:10:49 -0300
message:
  Implemented CollectionNames and DatabaseNames.
------------------------------------------------------------
revno: 72
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-08-01 23:21:24 -0300
message:
  Support for new tag convention.
------------------------------------------------------------
revno: 71
tags: r2011.07.28
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-07-28 22:00:22 -0300
message:
  DBRef support.
------------------------------------------------------------
revno: 70
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-07-28 21:54:31 -0300
message:
  Introductory docs.
------------------------------------------------------------
revno: 69
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-07-23 17:38:57 -0300
message:
  Adding doc.go.
------------------------------------------------------------
revno: 68
tags: r2011.07.15
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-07-15 20:44:48 -0400
message:
  New test ensuring batching+sort works.
------------------------------------------------------------
revno: 67
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-07-15 20:42:22 -0400
message:
  Fix bad wlock/rlock interaction in AcquireSocket.
------------------------------------------------------------
revno: 66
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-07-15 20:41:09 -0400
message:
  Disabled SetFinalizer in GridFS due to leak.
------------------------------------------------------------
revno: 65
tags: r2011.06.24
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-06-24 21:05:36 -0300
message:
  Speed up checkQueryError.
------------------------------------------------------------
revno: 64
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-06-24 21:01:58 -0300
message:
  Updated to current weekly.
------------------------------------------------------------
revno: 63
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-05-28 21:09:01 -0300
message:
  More doc fixes.
------------------------------------------------------------
revno: 62
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-05-28 20:34:13 -0300
message:
  Added a few other mentions of errmsg in the documentation.
------------------------------------------------------------
revno: 61
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-05-28 20:30:59 -0300
message:
  Fixed documentation of Find, as reported by Travis Reeder.
------------------------------------------------------------
revno: 60
tags: r2011.05.24
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-05-24 00:09:57 -0300
message:
  FindAndModify and Update/Upsert improvements.
------------------------------------------------------------
revno: 59
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-05-12 08:12:16 +0200
message:
  gofmt
------------------------------------------------------------
revno: 58
tags: r2011.05.12
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-05-12 08:07:06 +0200
message:
  MapReduce and Distinct support.
------------------------------------------------------------
revno: 57
tags: r2011.04.28
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-04-28 23:16:21 -0300
message:
  Several changes for release r2011.04.28:
  
  - mgo and gobson were ported to the weekly.2011-04-27 release of Go.
  
  - The Iter.For and Query.For methods will now return err == nil when
    they iterate successfully up to the last available element, rather
    than mgo.NotFound.
  
  - New Explain and Hint methods for query optimization:
  
    http://goneat.org/lp/mgo#Query.Explain
    http://goneat.org/lp/mgo#Query.Hint
  
  - GridFS support will now ensure an index exists on {"files_id", "n"}
    when the first file is created.
  
  - The new GridFSFile type was renamed to GridFile.
  
  - Other minor renamings continuing the consitency improvements:
  
    mgo.CollectStats(true) =>  mgo.SetStats(true)
    mgo.Debug(true) => mgo.SetDebug(true)
  
  - In addition to byte slices, gobson can now marshal and
    unmarshal byte arrays as binary BSON data.
------------------------------------------------------------
revno: 56
tags: r2011.04.24
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-04-25 01:56:36 -0300
message:
  Minor doc fixes again.
------------------------------------------------------------
revno: 55
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-04-25 01:24:38 -0300
message:
  Minor doc fixup.
------------------------------------------------------------
revno: 54
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-04-25 01:04:06 -0300
message:
  GridFS support.
------------------------------------------------------------
revno: 53
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-04-21 11:16:26 -0300
message:
  gofmt
------------------------------------------------------------
revno: 52
tags: r2011.04.19
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-04-19 21:19:43 -0300
message:
  Some methods renamed, and For.
------------------------------------------------------------
revno: 51
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-04-18 19:58:16 -0300
message:
  Better panic when using closed sessions.
------------------------------------------------------------
revno: 50
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-04-15 02:37:50 -0300
message:
  Moved some variables to the suite test file.
------------------------------------------------------------
revno: 49
tags: r2011.04.13
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-04-13 19:30:13 -0300
message:
  Add geospatial index support in GetIndexes() too.
------------------------------------------------------------
revno: 48
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-04-13 19:12:11 -0300
message:
  Improved EnsureIndex docs.
------------------------------------------------------------
revno: 47
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-04-13 18:55:13 -0300
message:
  Implemented support for spatial indexes.
------------------------------------------------------------
revno: 46
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-04-13 01:29:45 -0300
message:
  Fixed after int32 changes in gobson.
------------------------------------------------------------
revno: 45
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-04-13 01:17:22 -0300
message:
  New index methods, SetMode, etc.
------------------------------------------------------------
revno: 44
tags: r2011.04.09
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-04-09 13:55:59 -0300
message:
  Auth support, Login, Count, etc.
------------------------------------------------------------
revno: 43
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-04-02 13:38:17 -0300
message:
  Minor doc improvements.
------------------------------------------------------------
revno: 42
tags: r2011-03-24, r2011.03.24
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-03-24 03:38:41 -0300
message:
  Added connect=direct, SlaveOk support, and more.
  
  - Implemented support for connect=direct mongo option.
  - Added support for SlaveOk queries, so that Monotonic and
    Eventual sessions will also make optimal use of resources
    when going through a mongos server.
  - Pick a random slave with Monotonic and Eventual sessions.
  - Small improvements in the cluster synchronization logic.
------------------------------------------------------------
revno: 41
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-03-23 22:59:12 -0300
message:
  Retry short reads (bug reported by Brian Ketelsen)
------------------------------------------------------------
revno: 40
tags: r2011-03-20, r2011.03.20
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-03-20 08:32:28 -0300
message:
  Removed old stuff from IDEAS file.
------------------------------------------------------------
revno: 39
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-03-20 08:29:03 -0300
message:
  - Initial support for mongodb://-style urls.
  - When a port number isn't provided, default to 27017.
------------------------------------------------------------
revno: 38
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-03-19 19:05:37 -0300
message:
  Implemented Query.Select method.
------------------------------------------------------------
revno: 37
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-03-19 16:09:43 -0300
message:
  Minor tweak in Find's documentation.
------------------------------------------------------------
revno: 36
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-03-19 16:06:51 -0300
message:
  Added support for Find(nil), as an alternative to Find(bson.M{}).
------------------------------------------------------------
revno: 35
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-03-19 15:57:50 -0300
message:
  Switching style to plain gofmt.
------------------------------------------------------------
revno: 34
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-03-19 15:43:53 -0300
message:
  Implemented tailable iterators support.
------------------------------------------------------------
revno: 33
tags: r2011-03-17, r2011.03.17
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-03-17 07:26:32 -0300
message:
  Minor documentation updates.
------------------------------------------------------------
revno: 32
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-03-17 07:18:16 -0300
message:
  Updated to use gobson/bson.
------------------------------------------------------------
revno: 31
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-03-17 05:58:41 -0300
message:
  - The Run method is now primarily in the collection, as recommended
    by Gary Burd.
  - gobson's package is now named bson.
------------------------------------------------------------
revno: 30
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-03-17 00:11:31 -0300
message:
  Added Remove and RemoveAll methods.
------------------------------------------------------------
revno: 29
tags: r2011-03-15, r2011.03.15
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-03-15 17:15:28 -0300
message:
  Added the missing copyright/licensing notices to files.
------------------------------------------------------------
revno: 28
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-03-15 10:25:40 -0300
message:
  Fixed license text.
------------------------------------------------------------
revno: 27
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-03-15 01:18:14 -0300
message:
  Tweaked documentation for Mongo function.
------------------------------------------------------------
revno: 26
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-03-15 00:46:19 -0300
message:
  Fix gobson import.
------------------------------------------------------------
revno: 25
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 23:27:46 -0300
message:
  s/mongogo/mgo/; Evan Shaw beat me in using the former name.
------------------------------------------------------------
revno: 24
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 22:42:45 -0300
message:
  Fully qualified package as launchpad.net/mongogo
------------------------------------------------------------
revno: 23
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 22:03:00 -0300
message:
  Fully qualify it as launchpad.net/mongogo
------------------------------------------------------------
revno: 22
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 21:57:44 -0300
message:
  Implemented session.Upsert.
------------------------------------------------------------
revno: 21
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 21:46:36 -0300
message:
  Implemented session.UpdateAll.
------------------------------------------------------------
revno: 20
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 21:36:23 -0300
message:
  Implemented session.Update.
------------------------------------------------------------
revno: 19
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 19:49:59 -0300
message:
  Some doc updates in the session.
------------------------------------------------------------
revno: 18
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-03-14 19:06:49 -0300
message:
  Use integrated Cond support.  Woohay!
------------------------------------------------------------
revno: 17
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-02-14 00:53:20 -0200
message:
  Minor documentation tweaks.
------------------------------------------------------------
revno: 16
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-02-14 00:44:33 -0200
message:
  - Implemented synchronization timeout for sessions.
  - Fixed a bug on the way, which would prevent a connection to be
    established to a slave during sync in case the consistency setting
    did not require talking to a master.
  - Also had to fix a bug in session.acquireSocket, which was ignoring
    the error returned by the call to cluster.AcquireSocket.
------------------------------------------------------------
revno: 15
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-02-11 06:23:05 -0200
message:
  A couple of additional checks on the socket count on resync test.
------------------------------------------------------------
revno: 14
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Fri 2011-02-11 06:06:54 -0200
message:
  - Introduced cluster reference counting, so that it may be
    deterministically finalized when all sessions referring to it are
    closed.  When the last reference is gone, all servers in the
    cluster are closed.
  - Implemented session.Close().  It releases the socket, if any, and
    decreases the cluster reference count.
  - Changed implementation of session.Monotonic/Strong/Eventual so that
    they do not create new sessions.  Use New().Monotonic() when that's
    the intention.  This makes the creation of sessions more explicit,
    and thus encourages the use of explicit releasing of resources.
  - Statistics for sockets are not zeroed on ResetStats anymore, since they
    reflect absolute numbers which increase and decrease.
  - Renamed stats.SocketsInUse back to SocketRefs, and reintroduced
    SocketsInUse with correct semantics.  They mean different things.
  - Tests have been improved so that all sessions created are explicitly
    closed, and the suite teardown will error if any sockets are left
    alive by the suite.  No more messing around.
  - Fixed problems discovered by the more strict socket referencing
    checks.
------------------------------------------------------------
revno: 13
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-02-08 01:14:32 -0200
message:
  Implemented socket and server closing.  Now sockets will not pile up
  during a long cluster synchronization procedure.
------------------------------------------------------------
revno: 12
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-02-06 23:55:32 -0200
message:
  - Fixed timeout test (behavior of Mongo seems to have changed).
  - Fixed dropping of databases between tests.  Don't even know
    how it could be working before.
  - Use exec rather than os.StartProcess to run external commands,
    so that stdout may be captured and shown on errors.
  - Fixed primary shutdown test with monotonic session so that
    it necessarily connects to a slave.
  - Removed the passive mongo server from the replica set 2, since
    it looks like it's hitting a bug in Mongo:
  
    http://groups.google.com/group/mongodb-user/t/768d36ac9919e953
------------------------------------------------------------
revno: 11
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sat 2011-02-05 21:30:45 -0200
message:
  Introduced new tests and related fixes to verify the behavior
  of strong/monotonic/eventual consistency sessions while the
  primary server is shot down.
------------------------------------------------------------
revno: 10
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2011-01-17 23:21:53 -0200
message:
  - Prune dead sockets when attempting to acquire them.
  - Prune an erroring server and immediately start a resync in the background.
  - Shutting down the primary is now working.
  - Introduced the -fast flag to skip tests which take too long to run.
------------------------------------------------------------
revno: 9
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-01-16 22:30:44 -0200
message:
  Started implementing support for connection error handling and
  primary switching.  Test still broken.  Time to sleep now.
------------------------------------------------------------
revno: 8
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-01-13 23:16:45 -0200
message:
  Implemented session.Strong/Monotonic/Eventual methods.
------------------------------------------------------------
revno: 7
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-01-13 21:13:34 -0200
message:
  A few other minor tweaks.
------------------------------------------------------------
revno: 6
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Thu 2011-01-13 21:02:16 -0200
message:
  make gofmt
------------------------------------------------------------
revno: 5
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Wed 2011-01-12 00:21:55 -0200
message:
  Updated cond interface to the updated version submitted
  for inclusion in Go.
------------------------------------------------------------
revno: 4
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Tue 2011-01-11 22:53:52 -0200
message:
  - Implemented support for Safe() and Unsafe() in the session.
  - Better socket acquiring/releasing in the session.
  - Some minor method renaming.
------------------------------------------------------------
revno: 3
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Sun 2011-01-02 22:29:54 -0200
message:
  Progress on finding, iteration, sorting, etc.
------------------------------------------------------------
revno: 2
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2010-12-27 20:52:10 -0200
message:
  New session.Find(...).One/OneM() and session.Run/RunM() methods.
------------------------------------------------------------
revno: 1
committer: Gustavo Niemeyer <gustavo@niemeyer.net>
branch nick: trunk
timestamp: Mon 2010-12-27 15:38:02 -0200
message:
  Imported mongogo into repository.
------------------------------------------------------------
Use --include-merged or -n0 to see merged revisions.
