# monorepo-maven

Demo of a expanding/contracting monorepo

Created from this example:
https://paulhammant.com/2017/01/27/maven-in-a-google-style-monorepo/

Doing a 'quick' experiment with this repo/branch

Say that you goal is to only build/test 'settingsSpringboot' and 'settingsDropwizard', and not any of the other sub-modules that Maven were to recurse to by habit if run from the root level:

Initial setup:

git clone git@github.com:emurova/monorepo-maven.git
cd monorepo-maven

To run the experiment:

git config core.sparsecheckout true
echo '/mr' > .git/info/sparse-checkout
echo '/README.md' >> .git/info/sparse-checkout
echo '/pom*' >> .git/info/sparse-checkout
echo '/settingsSpringboot/' >> .git/info/sparse-checkout
echo '/settingsDropwizard/' >> .git/info/sparse-checkout
mr/checkout.sh
mvn install

You will have only those 2 modules code in your monorepo-maven folder.


