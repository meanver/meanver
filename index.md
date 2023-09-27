Meaningful Versions (meanver)
=============================

TL;DR
-----

progressbar 2.x gets released under the name progressbar2 AND imported as
`progressbar2` to match.  This allows it to coexist with other major versions.
If backwards compatibility means something other than API (e.g. code formatter)
then tell a story about what it means to you.

Definition
----------

We love semver, for languages that support its goals well.  This addition adapts
it for better Python compatibility in large-scale systems like monorepos.

1. Use semver where its recommendations do not conflict
2. Importable names need to be discoverable, so they MUST agree with the
   project name.

   a. Having documentation that says "import conffoo as cf" is against the
      spirit of this even if you also own the project "cf".

   b. Forks (that are "published" e.g. on pypi) MUST also rename.

   c. Integer suffixes MUST NOT be used except as in the following section.
      (Notably, this means forks MUST NOT just add a version)

3. Different major versions of a project MAY (from the beginning) and MUST (from
   2.x) use the major version as a suffix to the project name (thus by the point
   above, also importable name).

   a. For avoidance of doubt, this means 0.x and 1.x MAY use an unsuffixed name
      and this is intended to apply to "released versions" on some namespace
      e.g.  pypi (not source control repo names, branches, or zips published
      under a rock).

   b. If you have more than one importable name, you PROBABLY already have
      bigger problems, but the various names MUST be suffixed similarly.

4. The latest released versions of the unsuffixed and various
   major-verion-suffixed projects MUST be able to coexist (e.g. no duplicated
   unsuffixed names)
5. You MUST clearly declare what "backwards compatibility" means for your
   project.  Notably "backwards compatibility" does not always mean "identical
   output."
