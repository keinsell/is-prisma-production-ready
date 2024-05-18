# Is Prisma production ready?

Let's say you're newcommer in TypeScript ecosystem and you're looking to use ORM,
up to time of writting this you have two choices `MikroORM` which is based on
reflection and lack of any runtime safety will kick your ass once your project
will become mid-sized; And the second option is `Prisma` which resolves problems
of the previously mentioned one however adds quite a big set of new ones.

- `Prisma` do not support `CREATE_TYPE` of `postgres` (https://github.com/prisma/prisma/issues/4263)
- `Prisma` do not support `Union` Types which are useful for Polymorphic Relationships (https://github.com/prisma/prisma/issues/2505)
- `Prisma` do not support Polymorphic Relationships (https://github.com/prisma/prisma/issues/1644)
- `Prisma` do not support `groupBy` for queries (https://github.com/prisma/prisma/issues/6653)
- `Prisma` do not support recursive relationships (https://github.com/prisma/prisma/issues/3725)
- `Prisma` do not support soft deletions (https://github.com/prisma/prisma/issues/3398)
- `Prisma` do not support Row-Level Security (RLS) (https://github.com/prisma/prisma/issues/12735)

This are issues that I've personally experienced and got me stuck for a week or two in the past - eventually I've come
to conclusion to always add to application ORM and some query builder or tool for typesafe sql queries to not rely on
sole ORM as they often do not support multiple things and other things are barely portable to TypeScript in a favorable
manner. I'm not here to blame `prisma` as `typeorm` is way shittier even through `prisma` do not support a lot of
things they support well basics which are used by the most applications - BUT, there issues are in backlog for over
year and meanwhile instead fixes of issues we got *Prisma Accelerate* which will boost performance of your queries
- however, take on mind 10% queries which may be crucial for your application will not be supported.

GLHF, be responssible in the choice of your tech.
