The Strategy pattern defines a family of interchangeable algorithms. It allows a client to choose the algorithm from a family of algorithms at runtime.

>[!Example]
>In a Strategy pattern, you have a Context class that can switch between different Strategy objects. Each Strategy class implements a specific algorithm, and the Context class delegates its work to the chosen Strategy.

#design-patterns