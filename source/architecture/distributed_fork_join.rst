
Distributed Fork Join (DFJ)
===============================

H2O is the OpenSource Math and Prediction Platform for Big Data Science. H2O uses Distributed Fork/Join framework for fine-grain parallelism.
Fork/Join is Doug Lea's JSR166.

Fork/Join parallelism is among the simplest and most effective design techniques for obtaining good parallel performance.  Fork/join algorithms are parallel versions of familiar divide−and−conquer algorithms, taking the typical form::

    Result solve(Problem problem) {
        if (problem is small)
       	directly solve problem
       	else {
		split problem into independent parts
		fork new subtasks to solve each part
		join all subtasks
		compose result from subresults
       	}
     }

