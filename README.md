sf2-icu
=======

If you are using Symfony 2.1 on -say- *CentOS*, you might end up getting the unfamous exception ```The country resource bundle could not be loaded for locale "%s"```

Basically Symfony 2.1 uses version 49 of ICU, but some distributions (*CentOS* at least) only provide version 4.2!

There's been some discussion about the subject already : https://github.com/symfony/symfony/issues/5279,

but the *easy* solution of running ```php vendor/symfony/symfony/src/Symfony/Component/Locale/Resources/data/build-data.php 4.2``` requires you to have **(WTF)** *Subversion* installed on your machine/server.

Rather than doing so, grab the tarball of the compiled files form here : ```https://github.com/kbsali/sf2-icu/tarball/master``` and unpack it in ```vendor/symfony/symfony/src/Symfony/Component/Locale/Resources/data/```

Hope this helps.

Any other version needed?

How to install
==============

You could do something like that (kbsali-sf2-icu-XXXX depends on the sha of the last commit) :

```
wget https://github.com/kbsali/sf2-icu/tarball/master -O sf2-icu.tgz
tar xzvf sf2-icu.tgz
mv kbsali-sf2-icu-XXXX/4.2 vendor/symfony/symfony/src/Symfony/Component/Locale/Resources/data/
rm -rf kbsali-sf2-icu-XXXX sf2-icu.tgz
```
