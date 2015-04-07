Store
=====


_This project is no longer maintained and part of my source code "attic". Please use a [more mature and tested alternative](https://github.com/grevory/angular-local-storage). Feel free to use this though, works fine._

An Angular service providing two way binding to localStorage

Examples
--------

To create a two-way binding between localStorage and a controller's $scope, all you have to do is call Store#mirror.

    /**
     * Controls the plugin modal for installing and exploring plugins.
     */
    app.controller("MyController", ["$scope", "Store", function($scope, Store) {
    
	    $scope.model = Store.mirror($scope, "model", "model", {});
    
    }]);

Once that's done, any changes to $scope.model will propagate to localStorage.model and also the other way around. And because localStorage events are cross-window this will also create a cross-window binding.
