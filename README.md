# distributed system design

Single node patterns (application container assumes that it is talking to a service on localhost but communication is routed through another container)

1) Sidecar pattern - this pattern is used to add/enhance functionality of application containers (kind of decorator for app container). There are certain scenarios we can handle using this pattern-
* If we want to create separate reusable modules for authorization, authentication, encryption for example. These sidecar containers can be used by other application containers as they are independent and not tightly coupled.
* There are legacy applications that can't be upgraded easily or not being managed by any teams. Sidecar container can be added to app container without modifying legacy applications.

2) Ambassador pattern - this pattern is generally used as proxy for communication of application container to outside world. For example, if application container talks to database, caching service etc, this can be simple web server like nginx, apache if the only thing we are looking for is proxy. We can have some codebase as ambassador container if we need additional logic for routing, aggregation for example.
