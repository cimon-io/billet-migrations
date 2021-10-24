# Billet migrations

Standart migrations of [billet](https://github.com/cimon-io/billet) application which is able to be reused many times.

To add migration to your rails project, run:

```
bin/rails app:template LOCATION=https://raw.githubusercontent.com/cimon-io/billet-migrations/master/.billet.rb
```

And follow instructions.

# Available migrations

## Uid feild

Add autogenerated field which contains the UID.

## Counter cache

Add field `child_count` alike it counter_cache, but on database level.

## Belongs Directly

Lets say we have three tables which represent ActiveRecord models which belongs to each other. A `company` has many `projects`, a `project` has many `items`. This migration add field `company_id` to `items` table and keep it actual.

## Readable slug

Add field `slug` to generate it with incremental principle with mask `XX-AAA-0000` where `XX` -- two speciefic letters for a table and `AAA` letters which is unique for each day. For example, there are two tables `companies` and `projects` exists with prefixes `CO` and `PR`. The first company created will have slug `CO-SDF-0001`, the second one -- `CO-SDF-0002`. A project at the same day will have slug `PR-SDF-0001`, `PR-SDF-0002`, `PR-SDF-0003`, etc. Next day three letters prefix will be different. Lets say a company created next day will have slug `CO-TRW-0001`, `CO-TRW-0002`, etc. The projects next day will have slugs `PR-TRW-0001`, `PR-TRW-0002`, `PR-TRW-0003`, etc.

## Timestamps

Set default `CURRENT_TIMESTAMP` value for `created_at` and `updated_at` fields. Also updates `updated_at` field when record is changed or touched.

# Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/cimon-io/billet-migrations. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the Contributor Covenant code of conduct.

# License

The scripts are available as open source under the terms of the MIT License.
