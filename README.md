OpenShift SockJS test server
==================

To create this application, run the following command:

    rhc app-create sockjs nodejs --from-code https://github.com/matthicksj/sockjs.git

Next, clone the modified client harness that will just test the
websocket protocol:

    git clone https://github.com/matthicksj/sockjs-client.git

Change the test harness to use your domain and application name:

    export DOMAIN="your_domain_here"
    sed -ie "s/REPLACEDOMAIN/$DOMAIN/" sockjs-client/tests/config.js

Now, start the test harness

    make test

Lastly, open up a browser and run the qunit tests:

    http://localhost:8080/tests-qunit.html
