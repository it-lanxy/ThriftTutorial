Thrift installation
=======================================

Detailed information on how to install Thrift can be found here: http://thrift.apache.org/docs/install/

On Ubuntu Linux for example you just need to first install the dependencies and then you are ready to install Thrift.

	#. Install the languages with which you plan to use thrift. To use with Java for example, install a Java JDK you prefer. In this demo I am using Oracle JDK 7 for Ubuntu, but you shouldn't have problem using the one you like.
		* To use with Java you will also need to install Apache Ant ::
		
			sudo apt-get install ant


	#. Installing required tools and libraries: ::

		sudo apt-get install libboost-dev libboost-test-dev libboost-program-options-dev libboost-filesystem-dev libboost-thread-dev libevent-dev automake libtool flex bison pkg-config g++ libssl-dev

	* You can check for specific requirements for each language you wish to use here: http://thrift.apache.org/docs/install/

	#. Download Thrift: http://thrift.apache.org/download

	#. Copy the downloaded file into the desired directory and untar the file ::
				
		tar -xvf thrift-0.9.3.tar.gz
    
	#. For detailed instuctions on how to build Apache Thrift on your specific system you can read here: http://thrift.apache.org/docs/BuildingFromSource
	
		* For an Ubuntu linux distribution you just need to go to the thrift directory and type: ::

			./bootstrap.sh
			./configure
		
		* At the end of the output you should be able to see a list of all the libraries that are currently built in your system and ready to use with your desired programming languages. If a component is missing you should download the missing language and repeat the above step. ::
		
				thrift 0.9.3

				Building C++ Library ......... : yes
				Building C (GLib) Library .... : no
				Building Java Library ........ : yes
				Building C# Library .......... : no
				Building Python Library ...... : yes
				Building Ruby Library ........ : no
				Building Haskell Library ..... : no
				Building Perl Library ........ : no
				Building PHP Library ......... : no
				Building Erlang Library ...... : no
				Building Go Library .......... : no
				Building D Library ........... : no

				C++ Library:
				   Build TZlibTransport ...... : yes
				   Build TNonblockingServer .. : yes
				   Build TQTcpServer (Qt) .... : no

				Java Library:
				   Using javac ............... : javac
				   Using java ................ : java
				   Using ant ................. : /usr/bin/ant

				Python Library:
				   Using Python .............. : /usr/bin/python


		* Here http://thrift.apache.org/docs/install/debian/ you can find all the packages you might need to support your desired language in case some of them are missing.

		* On the same directory run make to build Thrift ::

			make
			
		* (Optional) Run the test suite if you want ::
		
			make check
			
		* And finally you are ready to install Thrift by running ::

			sudo make install

Verify installation
--------------------

Now your Thrift installation is completed! To verify that you have succesfully installed Thrift just type ::

	thrift -version

and you should be able to see something like the following: ::

	Thrift version 0.9.0

Additionaly you can go to the tutorial directory and follow the instructions located on the README files on each of the targeted languages directories. For example for JAVA you should be able to verify the following: ::

  thrift/tutorial/java$ file ../../lib/java/build/libthrift-${version}-${release}.jar 
  ../../lib/java/libthrift.jar: Zip archive data, at least v1.0 to extract

  thrift/tutorial/java$ file ../../compiler/cpp/thrift
  ../../compiler/cpp/thrift: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked (uses shared libs), for GNU/Linux 2.6.15, not stripped

  thrift/tutorial/java$ ls ../../lib/java/build/lib/
  commons-lang-2.5.jar  junit-4.4.jar  servlet-api-2.5.jar  slf4j-api-1.5.8.jar  slf4j-simple-1.5.8.jar



.. toctree::
   :maxdepth: 2
   

