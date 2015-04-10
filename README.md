Map-reduce k-means algorithm using radical-pilot tools
======================================================


<h1> Requirements: </h1>

<h3> Install Python </h3>

RADICAL-Pilot needs Python >= 2.6. All dependencies are installed automatically by the installer. Besides that, RADICAL-Pilot needs access to a MongoDB database that is reachable from the internet. User groups within the same institution or project can share a single MongoDB instance.

<h3>Create a virtual environment: </h3>

```
virtualenv $HOME/myenv
source $HOME/myenv/bin/activate
```

<h3>Install radical.pilot module: </h3>

```
pip install radical.pilot:
```

<h3> Install MongoDB: </h3>

- This step is not mandatory if you are going to run MongoDB remotely

Linux User:

```
apt-get -y install scons libssl-dev libboost-filesystem-dev libboost-program-options-dev libboost-system-dev libboost-thread-dev
git clone -b r2.6.3 https://github.com/mongodb/mongo.git
cd mongo
scons --64 --ssl all
scons --64 --ssl --prefix=/usr install
```
Mac User:

```
brew install mongodb --with-openssl
```
then: Crete a Data directory:
```
mkdir -p /data/db
```
set read & write permissions to this folder:
```
chmod 755 /data/db
```
Run MongodB:
```
mongod
```

<h1>Hands-On Job Submission </h1>

In order to make this example work, we need first to activate your virtualenv:

```
source $HOME/myenv/bin/activate
```

<h3> Download the mpk-k-means  via command line: </h3>

```
curl -LOk https://github.com/georgeha/k-means-map-reduce/archive/master.zip 
```

Unzip:

```
tar -xf master.zip
```

move to the working directory:

```
cd k-means-map-reduce-master/
``` 

<h3> RUN! </h3>

```
python mpk-k-means.py 4
```

When you finish execution you are going to see on Terminal the new centroids. Also, a file
is also created at your working directory called centroids.data with the centroids.





