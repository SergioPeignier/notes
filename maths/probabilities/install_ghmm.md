# [Install GHMM General Hidden Markov Model](http://ghmm.sourceforge.net/installation.html)

+ Download the source code from the authors [repository](https://sourceforge.net/projects/ghmm/?source=typ_redirect)
+ Install swig: `conda install -c anaconda swig=3.0.10` (python wrapper)
+ uncompress the tar
+ sh autogen.sh
+ ./configure --without-python
+ make
+ make install
+ cd ghmmwrapper
+ python setup.py build
+ python setup.py install

# Some problems relates to libxml appeared so I needed to:
+ brew update 
+ brew uninstall libxml2
+ brew install libxml2 --with-xml2-config
+ brew link --force libxml2 