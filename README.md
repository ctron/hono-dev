# Developer tools for Eclipse Hono™

This is just my personal stuff, helping me to work on [Eclipse Hono](https://github.com/eclipse/hono).

## Eclipse Launchers

This repository hosts a set of Eclipse IDE launchers. In order to use them:

1. Install the Docker tools, M2Eclipse support into your Eclipe Java IDE
1. Clone the following repositories into your workspace and import their projects
   using the import wizard:
     * https://github.com/ctron/hono-dev
     * https://github.com/eclipse/hono
     * https://github.com/ctron/hono-simulator
1. Run "Qpid (Build Router Image)" at least once, in order to build the
   customized router image

After that you can run the Hono applications or the simulator applications. Be
sure to start all Hono services and the consumer before starting the simulator. 