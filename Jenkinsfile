// checkout and build the boost 1.57 version
node {
    // checkout code from repo
    checkout scm
    // save the present working directory as a variable
    def workspace = pwd() 
    // run the build script
    stage "Initiate Submodules"
    sh """
        #./scripts/install.sh
        #./scripts/build_test_run.sh
        # initiate the submodules
        git submodule update --init --recursive
    """

    stage "Build Boost"
    sh """
        # initiate and build the boost submodule
        #cd ${workspace}/lib/boost_1_57_0
        #git submodule init
        #git submodule update
        ./bootstrap.sh
        ./b2
        # return to the project directory
        cd ../../
    """
}
