### Intro
Remix.run like every framework has it own conventions, mainly related to routing. 

##### Special files
- ``remix.config.js`` Config file used by remix
- ``app/entry.server.{ts,tsx,js,jsx}`` Server rendering piece of remix
- ``app/entry.client.{ts,tsx,js,jsx}`` Client rendering/hydration piece of remix

##### ``Root.tsx``
This file, must be present inside the ``app/``  directory. It should contain your main layout. It should not contain essential modules used everywhere, as this file can be overwritten by another layout route.
	
This file accepts: ``loader``, ``action``, ``meta``, ``headers``, ``links``, ``ErrorBoundary`` component and ``CatchBoundary`` component. 
On of the exported components should be ``<Outlet />`` as it will contain the rest of your app access routes.




