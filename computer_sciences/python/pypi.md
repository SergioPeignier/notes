#Pypi
[useful link](http://peterdowns.com/posts/first-time-with-pypi.html)
[Pypi documentation](https://setuptools.readthedocs.io/en/latest/setuptools.html#automatic-script-creation)
[Basic commands documentation](https://wiki.python.org/moin/TestPyPI)
[install dependencies](http://python-packaging.readthedocs.io/en/latest/dependencies.html)
## Basic idea:
+ Register in both websited TesPypi and Pypi
+ Fill in your PyPI credentials in your ~/.pypirc file:
`[distutils]
index-servers=
    pypi
    pypitest

[pypitest]
repository = https://testpypi.python.org/pypi
username = <your user name goes here>
password = <your password goes here>

[pypi]
repository = https://pypi.python.org/pypi
username = <your user name goes here>
password = <your password goes here>`
+ Register your project (it allows you to modify your project on the server)
+ Upload
+ Download
+ Do the 3 previous operations first for TestPypi and only then for Pypi

## Register:
`python setup.py register -r pypitest`
`python setup.py register -r pypi`

## Upload:
`python setup.py sdist upload -r pypitest`
`python setup.py sdist upload -r pypi`

## Download:
`pip install -i https://testpypi.python.org/pypi nayesdog`
`pip install nayesdog`

## Uninstall:
`pip uninstall nayesdog`

## Remove packages from Pypi:
+ Login.
+ Go to your packages.
+ Check the "remove" checkbox for the particular package.
+ Click "Remove" button.
+ However You cannot upload a program with the same version!

## Setup example:
[documentation](https://docs.python.org/2/distutils/setupscript.html)

`from distutils.core import setup
setup(
    name = 'nayesdog',
    packages = ['nayesdog'],
    version = '0.1.1.0',
    description = 'RSS reader with Naive Bayes powered recommendations',
    author = 'Ilya Prokin, Sergio Peignier',
    author_email = 'isprokin@gmail.com, sergio.peignier.zapata@gmail.com',
    url = 'http://github.com/MLdog/nayesdog',
    download_url ='http://github.com/MLdog/nayesdog/tarball/0.1',
    keywords = ['RSS reader', 'Naive Bayes', 'recommendations'],
    classifiers = [],
    package_data = {'nayesdog':['icons/*','css.css','stopwords.txt']},
    scripts=['nayesdog/NayesDog'],
    install_requires=['feedparser']
)`

## Ideas to keep in mind while writing your scripts

+ In order to decrease dependency problems try to import only a few external modules (list of modules in [standard library](https://docs.python.org/2/library://docs.python.org/2/library/)) 
+ The data specified in `package_data` is stored with the rest of the library
+ The scripts specified by `script` option are stored in a different location
+ If you need to call your data in the library modules or functions, you cannot call them in a relative way as if the data was in the current directory.You can retrieve the location of the module you can use `imp.find_module` and then join the path:
`def get_name_in_library(name,module_name="nayesdog"):
    library_location = imp.find_module(module_name)[1]
    return os.path.join(library_location, name)`

+ If you need to write a module (default config file for example) and then import it you can write the module and the load it with:
`mod = importlib.import_module(testName)`
It is possible that you will need to updat the path `import sys; sys.path.append(".")`

##[Setup tools](http://setuptools.readthedocs.io/en/latest/setuptools.html#declaring-dependencies)
[difference with disutils](http://stackoverflow.com/questions/6344076/differences-between-distribute-distutils-setuptools-and-distutils2)
[same topic](http://stackoverflow.com/questions/25337706/setuptools-vs-distutils-why-is-distutils-still-a-thing)
