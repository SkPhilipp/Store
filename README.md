Store
=====

An Angular service providing two way binding to localStorage

Examples
--------

To create a two-way binding between localStorage and a controller's $scope, all you have to do is call Store#mirror.

    /**
     * Controls the plugin modal for installing and exploring plugins.
     */
    app.controller("MyController", ["$scope", "Store", function($scope, Store) {
    
	    $scope.model = Store.mirror($scope, "model", {});
    
    }]);

Once that's done, any changes to $scope.model will propagate to localStorage.model and also the other way around. And because localStorage events are cross-window this will also create a cross-window binding.

Also, in case you don't want to use the same name in localStorage you can call Store#mirror as follows

    $scope.model = Store.mirror($scope, "model", "totallyCustomName") || {};
