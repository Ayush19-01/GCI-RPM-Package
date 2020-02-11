# GCI-RPM-Package
1) Create your module/python programme.For me it is a  simple hello world program 'hello.py'.

2) Create a directory ('Packaging' for me), and further create a sub-directory ('test_pkg' for me) which will hold the '__init__.py' file and hello world program.

3) In the 'Packaging' directory, create two more files--> setup.py and README.md. The following code is required for setup.py:
    
```import setuptools

with open("README.md", "r") as fh:
    long_description = fh.read()

setuptools.setup(
    name="example-pkg-YOUR-USERNAME-HERE", # Replace with your own username
    version="0.0.1",
    author="Example Author",
    author_email="author@example.com",
    description="A small example package",
    long_description=long_description,
    long_description_content_type="text/markdown",
    url="https://github.com/pypa/sampleproject",
    packages=setuptools.find_packages(),
    classifiers=[
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
        "Operating System :: OS Independent",
    ],
    python_requires='>=3.6',)
 ```
4) Replace all the placehoders with appropriate values of your choice

5) Open a terminal window and move to the 'Packaging' directory. Run the command 'python setup.py bdist_rpm'.

6. There are three steps to building a binary RPM package, all of which are handled automatically by the Distutils:
  
    6.1 create a .spec file, which describes the package 
  
    6.2 create the source RPM
  
    6.3 create the "binary" RPM (which may or may not contain binary code, depending on whether your module distribution 
    contains Python extensions)


7) A new directory called 'build' should be created. Inside the 'build' folder, there is another folder 'bdist.macosx-10.7-x86_64' followed by another directory called 'rpm'. Inside rpm we have 5 folders. The SOURCES directory contains our tar.gz package, and in SPECS we will have our spec file.

That's a way to create a RPM package for a simple python file.
