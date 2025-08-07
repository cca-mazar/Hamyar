# Hamyar The First Motorbike Web Application In Afghanistan.

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RideSwift - Motorbike Delivery Platform</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        .app-transition { transition: all 0.3s ease-in-out; }
        .pulse-dot { animation: pulse 2s infinite; }
        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.5; }
        }
        .gradient-bg { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .card-shadow { box-shadow: 0 10px 25px rgba(0,0,0,0.1); }
        .map-container { background: linear-gradient(45deg, #e8f5e8, #f0f8f0); }
    </style>
</head>
<body class="bg-gray-50 font-sans">
    <!-- Navigation Header -->
    <nav class="gradient-bg text-white p-4 sticky top-0 z-50">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <i class="fas fa-motorcycle text-2xl"></i>
                <h1 class="text-xl font-bold">RideSwift</h1>
            </div>
            <div class="flex space-x-4">
                <button onclick="switchApp('customer')" class="app-btn px-4 py-2 rounded-lg bg-white/20 hover:bg-white/30 transition-all" data-app="customer">
                    <i class="fas fa-user mr-2"></i>Customer
                </button>
                <button onclick="switchApp('rider')" class="app-btn px-4 py-2 rounded-lg bg-white/20 hover:bg-white/30 transition-all" data-app="rider">
                    <i class="fas fa-motorcycle mr-2"></i>Rider
                </button>
                <button onclick="switchApp('admin')" class="app-btn px-4 py-2 rounded-lg bg-white/20 hover:bg-white/30 transition-all" data-app="admin">
                    <i class="fas fa-cog mr-2"></i>Admin
                </button>
            </div>
        </div>
    </nav>

    <!-- Customer App -->
    <div id="customer-app" class="app-container">
        <div class="max-w-6xl mx-auto p-6">
            <!-- Customer Dashboard -->
            <div class="grid md:grid-cols-3 gap-6 mb-8">
                <!-- Profile Card -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center space-x-4 mb-4">
                        <div class="w-16 h-16 bg-blue-500 rounded-full flex items-center justify-center text-white text-xl font-bold">
                            AK
                        </div>
                        <div>
                            <h3 class="font-semibold text-lg">Ahmad Khan</h3>
                            <p class="text-gray-600">+93 700 123 456</p>
                            <div class="flex items-center mt-1">
                                <i class="fas fa-shield-alt text-green-500 mr-1"></i>
                                <span class="text-sm text-green-600">Verified</span>
                            </div>
                        </div>
                    </div>
                    <button class="w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600 transition-all">
                        <i class="fas fa-edit mr-2"></i>Edit Profile
                    </button>
                </div>

                <!-- Wallet Card -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex justify-between items-center mb-4">
                        <h3 class="font-semibold text-lg">Wallet Balance</h3>
                        <i class="fas fa-wallet text-green-500 text-xl"></i>
                    </div>
                    <div class="text-3xl font-bold text-green-600 mb-4">2,450 AFN</div>
                    <button class="w-full bg-green-500 text-white py-2 rounded-lg hover:bg-green-600 transition-all">
                        <i class="fas fa-plus mr-2"></i>Add Money
                    </button>
                </div>

                <!-- Quick Stats -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="font-semibold text-lg mb-4">Quick Stats</h3>
                    <div class="space-y-3">
                        <div class="flex justify-between">
                            <span class="text-gray-600">Total Orders</span>
                            <span class="font-semibold">47</span>
                        </div>
                        <div class="flex justify-between">
                            <span class="text-gray-600">This Month</span>
                            <span class="font-semibold">8</span>
                        </div>
                        <div class="flex justify-between">
                            <span class="text-gray-600">Saved Addresses</span>
                            <span class="font-semibold">3</span>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Order Placement Section -->
            <div class="bg-white rounded-xl p-6 card-shadow mb-8">
                <h2 class="text-2xl font-bold mb-6">Place New Order</h2>
                
                <!-- Service Type Selection -->
                <div class="mb-6">
                    <label class="block text-sm font-medium mb-3">Service Type</label>
                    <div class="grid grid-cols-2 gap-4">
                        <button onclick="selectService('package')" class="service-btn p-4 border-2 border-gray-200 rounded-lg hover:border-blue-500 transition-all" data-service="package">
                            <i class="fas fa-box text-2xl text-blue-500 mb-2"></i>
                            <div class="font-semibold">Package Delivery</div>
                            <div class="text-sm text-gray-600">Send packages & documents</div>
                        </button>
                        <button onclick="selectService('ride')" class="service-btn p-4 border-2 border-gray-200 rounded-lg hover:border-blue-500 transition-all" data-service="ride">
                            <i class="fas fa-user text-2xl text-green-500 mb-2"></i>
                            <div class="font-semibold">Solo Ride</div>
                            <div class="text-sm text-gray-600">Personal transportation</div>
                        </button>
                    </div>
                </div>

                <!-- Location Selection -->
                <div class="grid md:grid-cols-2 gap-6 mb-6">
                    <div>
                        <label class="block text-sm font-medium mb-2">Pickup Location</label>
                        <div class="relative">
                            <input type="text" placeholder="Enter pickup address" class="w-full p-3 border border-gray-300 rounded-lg pl-10">
                            <i class="fas fa-map-marker-alt absolute left-3 top-4 text-green-500"></i>
                        </div>
                    </div>
                    <div>
                        <label class="block text-sm font-medium mb-2">Drop-off Location</label>
                        <div class="relative">
                            <input type="text" placeholder="Enter destination address" class="w-full p-3 border border-gray-300 rounded-lg pl-10">
                            <i class="fas fa-map-marker-alt absolute left-3 top-4 text-red-500"></i>
                        </div>
                    </div>
                </div>

                <!-- Map Display -->
                <div class="map-container h-64 rounded-lg mb-6 flex items-center justify-center border-2 border-dashed border-gray-300">
                    <div class="text-center">
                        <i class="fas fa-map text-4xl text-gray-400 mb-2"></i>
                        <p class="text-gray-600">Interactive map will appear here</p>
                        <p class="text-sm text-gray-500">Select pickup and drop-off points</p>
                    </div>
                </div>

                <!-- Package Details (shown when package service is selected) -->
                <div id="package-details" class="hidden mb-6">
                    <h3 class="font-semibold mb-4">Package Details</h3>
                    <div class="grid md:grid-cols-2 gap-4 mb-4">
                        <select class="p-3 border border-gray-300 rounded-lg">
                            <option>Package Size</option>
                            <option>Small (up to 2kg)</option>
                            <option>Medium (2-5kg)</option>
                            <option>Large (5-10kg)</option>
                        </select>
                        <input type="text" placeholder="Package description" class="p-3 border border-gray-300 rounded-lg">
                    </div>
                    <div class="border-2 border-dashed border-gray-300 rounded-lg p-6 text-center">
                        <i class="fas fa-camera text-2xl text-gray-400 mb-2"></i>
                        <p class="text-gray-600">Upload package photo</p>
                        <button class="mt-2 px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">Choose Photo</button>
                    </div>
                </div>

                <!-- Fare Calculation -->
                <div class="bg-gray-50 rounded-lg p-4 mb-6">
                    <div class="flex justify-between items-center mb-2">
                        <span>Distance</span>
                        <span class="font-semibold">5.2 km</span>
                    </div>
                    <div class="flex justify-between items-center mb-2">
                        <span>Base Fare</span>
                        <span class="font-semibold">52 AFN</span>
                    </div>
                    <div class="flex justify-between items-center mb-2">
                        <span>Service Fee</span>
                        <span class="font-semibold">15 AFN</span>
                    </div>
                    <div class="border-t pt-2 flex justify-between items-center font-bold text-lg">
                        <span>Total Fare</span>
                        <span class="text-green-600">67 AFN</span>
                    </div>
                    <div class="text-sm text-gray-600 mt-2">
                        <i class="fas fa-clock mr-1"></i>Estimated delivery: 25-30 minutes
                    </div>
                </div>

                <!-- Payment Method -->
                <div class="mb-6">
                    <label class="block text-sm font-medium mb-3">Payment Method</label>
                    <div class="space-y-2">
                        <label class="flex items-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-gray-50">
                            <input type="radio" name="payment" value="wallet" class="mr-3" checked>
                            <i class="fas fa-wallet text-green-500 mr-3"></i>
                            <span>Wallet Balance (2,450 AFN)</span>
                        </label>
                        <label class="flex items-center p-3 border border-gray-300 rounded-lg cursor-pointer hover:bg-gray-50">
                            <input type="radio" name="payment" value="cash" class="mr-3">
                            <i class="fas fa-money-bill text-blue-500 mr-3"></i>
                            <span>Cash on Delivery</span>
                        </label>
                    </div>
                </div>

                <button onclick="placeOrder()" class="w-full bg-gradient-to-r from-blue-500 to-purple-600 text-white py-4 rounded-lg font-semibold text-lg hover:from-blue-600 hover:to-purple-700 transition-all">
                    <i class="fas fa-paper-plane mr-2"></i>Place Order
                </button>
            </div>

            <!-- Active Orders -->
            <div class="bg-white rounded-xl p-6 card-shadow mb-8">
                <h2 class="text-2xl font-bold mb-6">Active Orders</h2>
                <div id="active-orders" class="space-y-4">
                    <!-- Active order will appear here -->
                </div>
                <div id="no-active-orders" class="text-center py-8 text-gray-500">
                    <i class="fas fa-clipboard-list text-4xl mb-4"></i>
                    <p>No active orders</p>
                </div>
            </div>

            <!-- Order History -->
            <div class="bg-white rounded-xl p-6 card-shadow">
                <h2 class="text-2xl font-bold mb-6">Recent Orders</h2>
                <div class="space-y-4">
                    <div class="flex items-center justify-between p-4 border border-gray-200 rounded-lg">
                        <div class="flex items-center space-x-4">
                            <div class="w-12 h-12 bg-green-100 rounded-full flex items-center justify-center">
                                <i class="fas fa-box text-green-600"></i>
                            </div>
                            <div>
                                <div class="font-semibold">Package to Shar-e-Naw</div>
                                <div class="text-sm text-gray-600">Delivered • 2 hours ago</div>
                                <div class="flex items-center mt-1">
                                    <div class="flex text-yellow-400">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                    </div>
                                    <span class="text-sm text-gray-600 ml-2">Excellent service!</span>
                                </div>
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="font-semibold">85 AFN</div>
                            <button class="text-blue-500 text-sm hover:underline">Reorder</button>
                        </div>
                    </div>

                    <div class="flex items-center justify-between p-4 border border-gray-200 rounded-lg">
                        <div class="flex items-center space-x-4">
                            <div class="w-12 h-12 bg-blue-100 rounded-full flex items-center justify-center">
                                <i class="fas fa-user text-blue-600"></i>
                            </div>
                            <div>
                                <div class="font-semibold">Ride to Kabul University</div>
                                <div class="text-sm text-gray-600">Completed • Yesterday</div>
                                <div class="flex items-center mt-1">
                                    <div class="flex text-yellow-400">
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="fas fa-star"></i>
                                        <i class="far fa-star"></i>
                                    </div>
                                    <span class="text-sm text-gray-600 ml-2">Good ride</span>
                                </div>
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="font-semibold">120 AFN</div>
                            <button class="text-blue-500 text-sm hover:underline">Book Again</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Rider App -->
    <div id="rider-app" class="app-container hidden">
        <div class="max-w-6xl mx-auto p-6">
            <!-- Rider Dashboard -->
            <div class="grid md:grid-cols-4 gap-6 mb-8">
                <!-- Status Card -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center justify-between mb-4">
                        <h3 class="font-semibold">Status</h3>
                        <div class="flex items-center">
                            <div class="w-3 h-3 bg-green-500 rounded-full pulse-dot mr-2"></div>
                            <span class="text-green-600 font-semibold">Online</span>
                        </div>
                    </div>
                    <button onclick="toggleRiderStatus()" class="w-full bg-red-500 text-white py-2 rounded-lg hover:bg-red-600 transition-all">
                        Go Offline
                    </button>
                </div>

                <!-- Today's Earnings -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="font-semibold mb-2">Today's Earnings</h3>
                    <div class="text-2xl font-bold text-green-600 mb-2">1,250 AFN</div>
                    <div class="text-sm text-gray-600">12 deliveries completed</div>
                </div>

                <!-- Rating -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="font-semibold mb-2">Your Rating</h3>
                    <div class="flex items-center mb-2">
                        <div class="text-2xl font-bold mr-2">4.8</div>
                        <div class="flex text-yellow-400">
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                            <i class="fas fa-star"></i>
                        </div>
                    </div>
                    <div class="text-sm text-gray-600">Based on 156 reviews</div>
                </div>

                <!-- Active Orders -->
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="font-semibold mb-2">Active Orders</h3>
                    <div class="text-2xl font-bold text-blue-600 mb-2">2</div>
                    <div class="text-sm text-gray-600">Max: 3 concurrent</div>
                </div>
            </div>

            <!-- Available Orders -->
            <div class="bg-white rounded-xl p-6 card-shadow mb-8">
                <div class="flex justify-between items-center mb-6">
                    <h2 class="text-2xl font-bold">Available Orders</h2>
                    <div class="flex items-center space-x-4">
                        <button class="px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                            <i class="fas fa-filter mr-2"></i>Filter
                        </button>
                        <button class="px-4 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                            <i class="fas fa-sync mr-2"></i>Refresh
                        </button>
                    </div>
                </div>

                <div class="space-y-4">
                    <!-- High Priority Order -->
                    <div class="border-2 border-yellow-400 bg-yellow-50 rounded-lg p-4">
                        <div class="flex justify-between items-start mb-3">
                            <div class="flex items-center space-x-2">
                                <span class="bg-yellow-400 text-white px-2 py-1 rounded text-xs font-semibold">HIGH PRIORITY</span>
                                <span class="bg-green-500 text-white px-2 py-1 rounded text-xs">Package</span>
                            </div>
                            <div class="text-right">
                                <div class="text-lg font-bold text-green-600">95 AFN</div>
                                <div class="text-sm text-gray-600">3.2 km</div>
                            </div>
                        </div>
                        <div class="grid md:grid-cols-2 gap-4 mb-3">
                            <div>
                                <div class="text-sm text-gray-600">Pickup</div>
                                <div class="font-semibold">Shahre Naw Park</div>
                                <div class="text-sm text-gray-500">2 min away</div>
                            </div>
                            <div>
                                <div class="text-sm text-gray-600">Drop-off</div>
                                <div class="font-semibold">Kabul University</div>
                                <div class="text-sm text-gray-500">15 min delivery</div>
                            </div>
                        </div>
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-4">
                                <div class="flex items-center">
                                    <i class="fas fa-user text-gray-400 mr-1"></i>
                                    <span class="text-sm">Ahmad K. (4.9★)</span>
                                </div>
                                <div class="flex items-center">
                                    <i class="fas fa-clock text-gray-400 mr-1"></i>
                                    <span class="text-sm">Posted 2 min ago</span>
                                </div>
                            </div>
                            <div class="flex space-x-2">
                                <button class="px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600">Decline</button>
                                <button onclick="acceptOrder()" class="px-6 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600 font-semibold">Accept</button>
                            </div>
                        </div>
                    </div>

                    <!-- Regular Order -->
                    <div class="border border-gray-200 rounded-lg p-4">
                        <div class="flex justify-between items-start mb-3">
                            <div class="flex items-center space-x-2">
                                <span class="bg-blue-500 text-white px-2 py-1 rounded text-xs">Ride</span>
                            </div>
                            <div class="text-right">
                                <div class="text-lg font-bold text-green-600">120 AFN</div>
                                <div class="text-sm text-gray-600">5.8 km</div>
                            </div>
                        </div>
                        <div class="grid md:grid-cols-2 gap-4 mb-3">
                            <div>
                                <div class="text-sm text-gray-600">Pickup</div>
                                <div class="font-semibold">Chicken Street</div>
                                <div class="text-sm text-gray-500">5 min away</div>
                            </div>
                            <div>
                                <div class="text-sm text-gray-600">Drop-off</div>
                                <div class="font-semibold">Bagh-e-Bala</div>
                                <div class="text-sm text-gray-500">20 min ride</div>
                            </div>
                        </div>
                        <div class="flex items-center justify-between">
                            <div class="flex items-center space-x-4">
                                <div class="flex items-center">
                                    <i class="fas fa-user text-gray-400 mr-1"></i>
                                    <span class="text-sm">Sara M. (4.7★)</span>
                                </div>
                                <div class="flex items-center">
                                    <i class="fas fa-clock text-gray-400 mr-1"></i>
                                    <span class="text-sm">Posted 5 min ago</span>
                                </div>
                            </div>
                            <div class="flex space-x-2">
                                <button class="px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600">Decline</button>
                                <button class="px-6 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600 font-semibold">Accept</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Current Deliveries -->
            <div id="current-deliveries" class="bg-white rounded-xl p-6 card-shadow mb-8 hidden">
                <h2 class="text-2xl font-bold mb-6">Current Deliveries</h2>
                <div class="space-y-4">
                    <div class="border-2 border-blue-500 bg-blue-50 rounded-lg p-4">
                        <div class="flex justify-between items-start mb-4">
                            <div>
                                <div class="flex items-center space-x-2 mb-2">
                                    <span class="bg-blue-500 text-white px-2 py-1 rounded text-xs font-semibold">IN PROGRESS</span>
                                    <span class="bg-yellow-400 text-white px-2 py-1 rounded text-xs">Package</span>
                                </div>
                                <div class="font-semibold text-lg">Shahre Naw Park → Kabul University</div>
                                <div class="text-sm text-gray-600">Order #RS-2024-001</div>
                            </div>
                            <div class="text-right">
                                <div class="text-lg font-bold text-green-600">95 AFN</div>
                                <div class="text-sm text-gray-600">3.2 km</div>
                            </div>
                        </div>

                        <!-- Navigation -->
                        <div class="bg-white rounded-lg p-4 mb-4">
                            <div class="flex items-center justify-between mb-3">
                                <h4 class="font-semibold">Navigation</h4>
                                <button class="text-blue-500 hover:underline">
                                    <i class="fas fa-route mr-1"></i>Alternative Route
                                </button>
                            </div>
                            <div class="map-container h-32 rounded-lg flex items-center justify-center">
                                <div class="text-center">
                                    <i class="fas fa-map text-2xl text-gray-400 mb-1"></i>
                                    <p class="text-sm text-gray-600">Turn right in 200m</p>
                                </div>
                            </div>
                        </div>

                        <!-- Customer Info -->
                        <div class="bg-white rounded-lg p-4 mb-4">
                            <div class="flex items-center justify-between">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center text-white font-bold">
                                        AK
                                    </div>
                                    <div>
                                        <div class="font-semibold">Ahmad Khan</div>
                                        <div class="text-sm text-gray-600">+93 700 123 456</div>
                                    </div>
                                </div>
                                <div class="flex space-x-2">
                                    <button class="p-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                                        <i class="fas fa-phone"></i>
                                    </button>
                                    <button class="p-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                                        <i class="fas fa-comment"></i>
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="flex space-x-3">
                            <button class="flex-1 bg-yellow-500 text-white py-3 rounded-lg hover:bg-yellow-600 font-semibold">
                                <i class="fas fa-map-marker-alt mr-2"></i>Arrived at Pickup
                            </button>
                            <button class="px-4 py-3 bg-red-500 text-white rounded-lg hover:bg-red-600">
                                <i class="fas fa-exclamation-triangle"></i>
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Earnings Summary -->
            <div class="grid md:grid-cols-2 gap-6">
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="text-xl font-bold mb-4">Weekly Earnings</h3>
                    <div class="space-y-3">
                        <div class="flex justify-between">
                            <span>Total Earnings</span>
                            <span class="font-semibold">8,750 AFN</span>
                        </div>
                        <div class="flex justify-between">
                            <span>Completed Orders</span>
                            <span class="font-semibold">67</span>
                        </div>
                        <div class="flex justify-between">
                            <span>Average per Order</span>
                            <span class="font-semibold">130 AFN</span>
                        </div>
                        <div class="flex justify-between text-red-600">
                            <span>Late Penalties</span>
                            <span class="font-semibold">-125 AFN</span>
                        </div>
                    </div>
                    <button class="w-full mt-4 bg-green-500 text-white py-2 rounded-lg hover:bg-green-600">
                        <i class="fas fa-download mr-2"></i>Request Payout
                    </button>
                </div>

                <div class="bg-white rounded-xl p-6 card-shadow">
                    <h3 class="text-xl font-bold mb-4">Safety & Support</h3>
                    <div class="space-y-3">
                        <button class="w-full bg-red-600 text-white py-3 rounded-lg hover:bg-red-700 font-semibold">
                            <i class="fas fa-exclamation-triangle mr-2"></i>Emergency SOS
                        </button>
                        <button class="w-full bg-orange-500 text-white py-3 rounded-lg hover:bg-orange-600">
                            <i class="fas fa-shield-alt mr-2"></i>I'm Not Safe
                        </button>
                        <button class="w-full bg-blue-500 text-white py-3 rounded-lg hover:bg-blue-600">
                            <i class="fas fa-headset mr-2"></i>Contact Support
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Admin Panel -->
    <div id="admin-app" class="app-container hidden">
        <div class="max-w-7xl mx-auto p-6">
            <!-- Admin Dashboard Stats -->
            <div class="grid md:grid-cols-4 gap-6 mb-8">
                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center justify-between">
                        <div>
                            <h3 class="text-sm font-medium text-gray-600">Total Orders</h3>
                            <div class="text-2xl font-bold">12,847</div>
                            <div class="text-sm text-green-600">+12% from last month</div>
                        </div>
                        <i class="fas fa-shopping-cart text-3xl text-blue-500"></i>
                    </div>
                </div>

                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center justify-between">
                        <div>
                            <h3 class="text-sm font-medium text-gray-600">Active Riders</h3>
                            <div class="text-2xl font-bold">234</div>
                            <div class="text-sm text-green-600">+8% from last week</div>
                        </div>
                        <i class="fas fa-motorcycle text-3xl text-green-500"></i>
                    </div>
                </div>

                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center justify-between">
                        <div>
                            <h3 class="text-sm font-medium text-gray-600">Revenue</h3>
                            <div class="text-2xl font-bold">1.2M AFN</div>
                            <div class="text-sm text-green-600">+15% from last month</div>
                        </div>
                        <i class="fas fa-chart-line text-3xl text-purple-500"></i>
                    </div>
                </div>

                <div class="bg-white rounded-xl p-6 card-shadow">
                    <div class="flex items-center justify-between">
                        <div>
                            <h3 class="text-sm font-medium text-gray-600">Customer Satisfaction</h3>
                            <div class="text-2xl font-bold">4.8/5</div>
                            <div class="text-sm text-green-600">+0.2 from last month</div>
                        </div>
                        <i class="fas fa-star text-3xl text-yellow-500"></i>
                    </div>
                </div>
            </div>

            <!-- Management Tabs -->
            <div class="bg-white rounded-xl card-shadow mb-8">
                <div class="border-b border-gray-200">
                    <nav class="flex space-x-8 px-6">
                        <button onclick="switchAdminTab('users')" class="admin-tab py-4 px-2 border-b-2 border-blue-500 text-blue-600 font-medium" data-tab="users">
                            User Management
                        </button>
                        <button onclick="switchAdminTab('orders')" class="admin-tab py-4 px-2 border-b-2 border-transparent text-gray-500 hover:text-gray-700" data-tab="orders">
                            Order Management
                        </button>
                        <button onclick="switchAdminTab('finance')" class="admin-tab py-4 px-2 border-b-2 border-transparent text-gray-500 hover:text-gray-700" data-tab="finance">
                            Financial Management
                        </button>
                        <button onclick="switchAdminTab('analytics')" class="admin-tab py-4 px-2 border-b-2 border-transparent text-gray-500 hover:text-gray-700" data-tab="analytics">
                            Analytics
                        </button>
                    </nav>
                </div>

                <!-- User Management Tab -->
                <div id="admin-users" class="admin-tab-content p-6">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-2xl font-bold">User Management</h2>
                        <div class="flex space-x-3">
                            <input type="text" placeholder="Search users..." class="px-4 py-2 border border-gray-300 rounded-lg">
                            <select class="px-4 py-2 border border-gray-300 rounded-lg">
                                <option>All Users</option>
                                <option>Customers</option>
                                <option>Riders</option>
                                <option>Pending Verification</option>
                            </select>
                        </div>
                    </div>

                    <!-- Pending Verifications -->
                    <div class="mb-8">
                        <h3 class="text-lg font-semibold mb-4 text-orange-600">Pending Verifications (3)</h3>
                        <div class="space-y-4">
                            <div class="border border-orange-200 bg-orange-50 rounded-lg p-4">
                                <div class="flex items-center justify-between">
                                    <div class="flex items-center space-x-4">
                                        <div class="w-12 h-12 bg-orange-500 rounded-full flex items-center justify-center text-white font-bold">
                                            MR
                                        </div>
                                        <div>
                                            <div class="font-semibold">Mohammad Rahman</div>
                                            <div class="text-sm text-gray-600">Rider Application</div>
                                            <div class="text-sm text-gray-500">Applied 2 hours ago</div>
                                        </div>
                                    </div>
                                    <div class="flex items-center space-x-3">
                                        <button class="px-4 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                                            <i class="fas fa-eye mr-2"></i>Review Documents
                                        </button>
                                        <button class="px-4 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                                            <i class="fas fa-check mr-2"></i>Approve
                                        </button>
                                        <button class="px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600">
                                            <i class="fas fa-times mr-2"></i>Reject
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Active Users -->
                    <div>
                        <h3 class="text-lg font-semibold mb-4">Active Users</h3>
                        <div class="overflow-x-auto">
                            <table class="w-full">
                                <thead class="bg-gray-50">
                                    <tr>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">User</th>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Type</th>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Rating</th>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Orders</th>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Status</th>
                                        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Actions</th>
                                    </tr>
                                </thead>
                                <tbody class="bg-white divide-y divide-gray-200">
                                    <tr>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="flex items-center">
                                                <div class="w-10 h-10 bg-blue-500 rounded-full flex items-center justify-center text-white font-bold">
                                                    AK
                                                </div>
                                                <div class="ml-4">
                                                    <div class="font-medium">Ahmad Khan</div>
                                                    <div class="text-sm text-gray-500">+93 700 123 456</div>
                                                </div>
                                            </div>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <span class="px-2 py-1 text-xs font-semibold rounded-full bg-blue-100 text-blue-800">Customer</span>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="flex items-center">
                                                <span class="text-yellow-400 mr-1">★</span>
                                                <span>4.9</span>
                                            </div>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">47</td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <span class="px-2 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800">Active</span>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                                            <button class="text-blue-600 hover:text-blue-900 mr-3">View</button>
                                            <button class="text-red-600 hover:text-red-900">Suspend</button>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="flex items-center">
                                                <div class="w-10 h-10 bg-green-500 rounded-full flex items-center justify-center text-white font-bold">
                                                    FA
                                                </div>
                                                <div class="ml-4">
                                                    <div class="font-medium">Farid Ahmad</div>
                                                    <div class="text-sm text-gray-500">+93 701 234 567</div>
                                                </div>
                                            </div>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <span class="px-2 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800">Rider</span>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <div class="flex items-center">
                                                <span class="text-yellow-400 mr-1">★</span>
                                                <span>4.8</span>
                                            </div>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap">156</td>
                                        <td class="px-6 py-4 whitespace-nowrap">
                                            <span class="px-2 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800">Online</span>
                                        </td>
                                        <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                                            <button class="text-blue-600 hover:text-blue-900 mr-3">View</button>
                                            <button class="text-red-600 hover:text-red-900">Suspend</button>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>

                <!-- Financial Management Tab -->
                <div id="admin-finance" class="admin-tab-content p-6 hidden">
                    <h2 class="text-2xl font-bold mb-6">Financial Management</h2>
                    
                    <!-- Revenue Overview -->
                    <div class="grid md:grid-cols-3 gap-6 mb-8">
                        <div class="bg-gradient-to-r from-green-400 to-green-600 text-white rounded-xl p-6">
                            <h3 class="text-lg font-semibold mb-2">Total Revenue</h3>
                            <div class="text-3xl font-bold">1,247,500 AFN</div>
                            <div class="text-sm opacity-90">This month</div>
                        </div>
                        <div class="bg-gradient-to-r from-blue-400 to-blue-600 text-white rounded-xl p-6">
                            <h3 class="text-lg font-semibold mb-2">Commission Earned</h3>
                            <div class="text-3xl font-bold">187,125 AFN</div>
                            <div class="text-sm opacity-90">15% average</div>
                        </div>
                        <div class="bg-gradient-to-r from-purple-400 to-purple-600 text-white rounded-xl p-6">
                            <h3 class="text-lg font-semibold mb-2">Pending Payouts</h3>
                            <div class="text-3xl font-bold">45,230 AFN</div>
                            <div class="text-sm opacity-90">23 riders</div>
                        </div>
                    </div>

                    <!-- Payout Requests -->
                    <div class="bg-white rounded-lg border border-gray-200 mb-8">
                        <div class="px-6 py-4 border-b border-gray-200">
                            <h3 class="text-lg font-semibold">Pending Payout Requests</h3>
                        </div>
                        <div class="divide-y divide-gray-200">
                            <div class="px-6 py-4 flex items-center justify-between">
                                <div class="flex items-center space-x-4">
                                    <div class="w-10 h-10 bg-green-500 rounded-full flex items-center justify-center text-white font-bold">
                                        FA
                                    </div>
                                    <div>
                                        <div class="font-medium">Farid Ahmad</div>
                                        <div class="text-sm text-gray-500">Requested 2 hours ago</div>
                                    </div>
                                </div>
                                <div class="flex items-center space-x-4">
                                    <div class="text-right">
                                        <div class="font-semibold">2,450 AFN</div>
                                        <div class="text-sm text-gray-500">Weekly earnings</div>
                                    </div>
                                    <div class="flex space-x-2">
                                        <button class="px-4 py-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                                            Approve
                                        </button>
                                        <button class="px-4 py-2 bg-red-500 text-white rounded-lg hover:bg-red-600">
                                            Reject
                                        </button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Commission Settings -->
                    <div class="bg-white rounded-lg border border-gray-200">
                        <div class="px-6 py-4 border-b border-gray-200">
                            <h3 class="text-lg font-semibold">Commission Settings</h3>
                        </div>
                        <div class="p-6">
                            <div class="grid md:grid-cols-2 gap-6">
                                <div>
                                    <label class="block text-sm font-medium mb-2">Store Commission (%)</label>
                                    <input type="number" value="15" class="w-full p-3 border border-gray-300 rounded-lg">
                                </div>
                                <div>
                                    <label class="block text-sm font-medium mb-2">Rider Service Fee (%)</label>
                                    <input type="number" value="5" class="w-full p-3 border border-gray-300 rounded-lg">
                                </div>
                            </div>
                            <button class="mt-4 px-6 py-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                                Update Settings
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Analytics Tab -->
                <div id="admin-analytics" class="admin-tab-content p-6 hidden">
                    <h2 class="text-2xl font-bold mb-6">Analytics & Insights</h2>
                    
                    <!-- Key Metrics -->
                    <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-6 mb-8">
                        <div class="bg-white rounded-lg p-6 border border-gray-200">
                            <div class="flex items-center justify-between">
                                <div>
                                    <p class="text-sm text-gray-600">Avg Delivery Time</p>
                                    <p class="text-2xl font-bold">23 min</p>
                                </div>
                                <i class="fas fa-clock text-2xl text-blue-500"></i>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg p-6 border border-gray-200">
                            <div class="flex items-center justify-between">
                                <div>
                                    <p class="text-sm text-gray-600">Success Rate</p>
                                    <p class="text-2xl font-bold">97.8%</p>
                                </div>
                                <i class="fas fa-check-circle text-2xl text-green-500"></i>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg p-6 border border-gray-200">
                            <div class="flex items-center justify-between">
                                <div>
                                    <p class="text-sm text-gray-600">Peak Hours</p>
                                    <p class="text-2xl font-bold">12-2 PM</p>
                                </div>
                                <i class="fas fa-chart-bar text-2xl text-purple-500"></i>
                            </div>
                        </div>
                        <div class="bg-white rounded-lg p-6 border border-gray-200">
                            <div class="flex items-center justify-between">
                                <div>
                                    <p class="text-sm text-gray-600">Repeat Customers</p>
                                    <p class="text-2xl font-bold">68%</p>
                                </div>
                                <i class="fas fa-users text-2xl text-orange-500"></i>
                            </div>
                        </div>
                    </div>

                    <!-- High Demand Areas -->
                    <div class="bg-white rounded-lg border border-gray-200 mb-8">
                        <div class="px-6 py-4 border-b border-gray-200">
                            <h3 class="text-lg font-semibold">High Demand Areas</h3>
                        </div>
                        <div class="p-6">
                            <div class="space-y-4">
                                <div class="flex items-center justify-between p-3 bg-red-50 rounded-lg">
                                    <div>
                                        <div class="font-medium">Shahre Naw</div>
                                        <div class="text-sm text-gray-600">Commercial district</div>
                                    </div>
                                    <div class="text-right">
                                        <div class="font-bold text-red-600">847 orders</div>
                                        <div class="text-sm text-gray-600">This week</div>
                                    </div>
                                </div>
                                <div class="flex items-center justify-between p-3 bg-orange-50 rounded-lg">
                                    <div>
                                        <div class="font-medium">Wazir Akbar Khan</div>
                                        <div class="text-sm text-gray-600">Diplomatic area</div>
                                    </div>
                                    <div class="text-right">
                                        <div class="font-bold text-orange-600">623 orders</div>
                                        <div class="text-sm text-gray-600">This week</div>
                                    </div>
                                </div>
                                <div class="flex items-center justify-between p-3 bg-yellow-50 rounded-lg">
                                    <div>
                                        <div class="font-medium">Kabul University</div>
                                        <div class="text-sm text-gray-600">Educational hub</div>
                                    </div>
                                    <div class="text-right">
                                        <div class="font-bold text-yellow-600">456 orders</div>
                                        <div class="text-sm text-gray-600">This week</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Dynamic Pricing Suggestions -->
                    <div class="bg-white rounded-lg border border-gray-200">
                        <div class="px-6 py-4 border-b border-gray-200">
                            <h3 class="text-lg font-semibold">Dynamic Pricing Suggestions</h3>
                        </div>
                        <div class="p-6">
                            <div class="space-y-4">
                                <div class="flex items-center justify-between p-4 bg-blue-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <i class="fas fa-cloud-rain text-blue-500 text-xl"></i>
                                        <div>
                                            <div class="font-medium">Rainy Weather Surge</div>
                                            <div class="text-sm text-gray-600">Heavy rain expected tomorrow</div>
                                        </div>
                                    </div>
                                    <div class="text-right">
                                        <div class="font-bold text-blue-600">+25% pricing</div>
                                        <button class="text-sm text-blue-600 hover:underline">Apply</button>
                                    </div>
                                </div>
                                <div class="flex items-center justify-between p-4 bg-green-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <i class="fas fa-clock text-green-500 text-xl"></i>
                                        <div>
                                            <div class="font-medium">Peak Hour Adjustment</div>
                                            <div class="text-sm text-gray-600">High demand during lunch hours</div>
                                        </div>
                                    </div>
                                    <div class="text-right">
                                        <div class="font-bold text-green-600">+15% pricing</div>
                                        <button class="text-sm text-green-600 hover:underline">Apply</button>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Orders Tab -->
                <div id="admin-orders" class="admin-tab-content p-6 hidden">
                    <h2 class="text-2xl font-bold mb-6">Order Management</h2>
                    
                    <!-- Order Filters -->
                    <div class="flex space-x-4 mb-6">
                        <select class="px-4 py-2 border border-gray-300 rounded-lg">
                            <option>All Orders</option>
                            <option>Active</option>
                            <option>Completed</option>
                            <option>Cancelled</option>
                            <option>Disputed</option>
                        </select>
                        <input type="date" class="px-4 py-2 border border-gray-300 rounded-lg">
                        <input type="text" placeholder="Search orders..." class="px-4 py-2 border border-gray-300 rounded-lg">
                    </div>

                    <!-- Orders Table -->
                    <div class="bg-white rounded-lg border border-gray-200 overflow-hidden">
                        <table class="w-full">
                            <thead class="bg-gray-50">
                                <tr>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Order ID</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Customer</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Rider</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Amount</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Status</th>
                                    <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">Actions</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-gray-200">
                                <tr>
                                    <td class="px-6 py-4 whitespace-nowrap font-mono text-sm">#RS-2024-001</td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div class="text-sm font-medium">Ahmad Khan</div>
                                        <div class="text-sm text-gray-500">Package Delivery</div>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div class="text-sm font-medium">Farid Ahmad</div>
                                        <div class="text-sm text-gray-500">★ 4.8</div>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap font-semibold">95 AFN</td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <span class="px-2 py-1 text-xs font-semibold rounded-full bg-blue-100 text-blue-800">In Progress</span>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm">
                                        <button class="text-blue-600 hover:text-blue-900 mr-3">Track</button>
                                        <button class="text-red-600 hover:text-red-900">Cancel</button>
                                    </td>
                                </tr>
                                <tr>
                                    <td class="px-6 py-4 whitespace-nowrap font-mono text-sm">#RS-2024-002</td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div class="text-sm font-medium">Sara Mohammadi</div>
                                        <div class="text-sm text-gray-500">Solo Ride</div>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <div class="text-sm font-medium">Hassan Ali</div>
                                        <div class="text-sm text-gray-500">★ 4.9</div>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap font-semibold">120 AFN</td>
                                    <td class="px-6 py-4 whitespace-nowrap">
                                        <span class="px-2 py-1 text-xs font-semibold rounded-full bg-green-100 text-green-800">Completed</span>
                                    </td>
                                    <td class="px-6 py-4 whitespace-nowrap text-sm">
                                        <button class="text-blue-600 hover:text-blue-900 mr-3">View</button>
                                        <button class="text-gray-400">-</button>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Order Tracking Modal -->
    <div id="tracking-modal" class="fixed inset-0 bg-black bg-opacity-50 hidden items-center justify-center z-50">
        <div class="bg-white rounded-xl p-6 max-w-md w-full mx-4">
            <div class="flex justify-between items-center mb-4">
                <h3 class="text-xl font-bold">Order Tracking</h3>
                <button onclick="closeTrackingModal()" class="text-gray-500 hover:text-gray-700">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div class="space-y-4">
                <div class="flex items-center space-x-3">
                    <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center text-white">
                        <i class="fas fa-check text-sm"></i>
                    </div>
                    <div>
                        <div class="font-semibold">Order Confirmed</div>
                        <div class="text-sm text-gray-600">2:30 PM</div>
                    </div>
                </div>
                
                <div class="flex items-center space-x-3">
                    <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center text-white">
                        <i class="fas fa-check text-sm"></i>
                    </div>
                    <div>
                        <div class="font-semibold">Rider Assigned</div>
                        <div class="text-sm text-gray-600">2:32 PM - Farid Ahmad</div>
                    </div>
                </div>
                
                <div class="flex items-center space-x-3">
                    <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center text-white pulse-dot">
                        <i class="fas fa-motorcycle text-sm"></i>
                    </div>
                    <div>
                        <div class="font-semibold">En Route to Pickup</div>
                        <div class="text-sm text-gray-600">ETA: 3 minutes</div>
                    </div>
                </div>
                
                <div class="flex items-center space-x-3">
                    <div class="w-8 h-8 bg-gray-300 rounded-full flex items-center justify-center text-gray-600">
                        <i class="fas fa-box text-sm"></i>
                    </div>
                    <div>
                        <div class="font-semibold text-gray-500">Package Picked Up</div>
                        <div class="text-sm text-gray-400">Pending</div>
                    </div>
                </div>
                
                <div class="flex items-center space-x-3">
                    <div class="w-8 h-8 bg-gray-300 rounded-full flex items-center justify-center text-gray-600">
                        <i class="fas fa-flag-checkered text-sm"></i>
                    </div>
                    <div>
                        <div class="font-semibold text-gray-500">Delivered</div>
                        <div class="text-sm text-gray-400">Pending</div>
                    </div>
                </div>
            </div>
            
            <div class="mt-6 p-4 bg-blue-50 rounded-lg">
                <div class="flex items-center justify-between">
                    <div>
                        <div class="font-semibold">Farid Ahmad</div>
                        <div class="text-sm text-gray-600">★ 4.8 • Honda 125</div>
                    </div>
                    <div class="flex space-x-2">
                        <button class="p-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                            <i class="fas fa-phone"></i>
                        </button>
                        <button class="p-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                            <i class="fas fa-comment"></i>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // App switching functionality
        function switchApp(appName) {
            // Hide all apps
            document.querySelectorAll('.app-container').forEach(app => {
                app.classList.add('hidden');
            });
            
            // Show selected app
            document.getElementById(appName + '-app').classList.remove('hidden');
            
            // Update button states
            document.querySelectorAll('.app-btn').forEach(btn => {
                btn.classList.remove('bg-white/40');
                btn.classList.add('bg-white/20');
            });
            
            document.querySelector(`[data-app="${appName}"]`).classList.remove('bg-white/20');
            document.querySelector(`[data-app="${appName}"]`).classList.add('bg-white/40');
        }

        // Service selection
        function selectService(serviceType) {
            document.querySelectorAll('.service-btn').forEach(btn => {
                btn.classList.remove('border-blue-500', 'bg-blue-50');
                btn.classList.add('border-gray-200');
            });
            
            document.querySelector(`[data-service="${serviceType}"]`).classList.add('border-blue-500', 'bg-blue-50');
            
            // Show/hide package details
            const packageDetails = document.getElementById('package-details');
            if (serviceType === 'package') {
                packageDetails.classList.remove('hidden');
            } else {
                packageDetails.classList.add('hidden');
            }
        }

        // Place order functionality
        function placeOrder() {
            // Hide no active orders message
            document.getElementById('no-active-orders').classList.add('hidden');
            
            // Show active order
            const activeOrdersContainer = document.getElementById('active-orders');
            activeOrdersContainer.innerHTML = `
                <div class="border-2 border-blue-500 bg-blue-50 rounded-lg p-4">
                    <div class="flex justify-between items-start mb-4">
                        <div>
                            <div class="flex items-center space-x-2 mb-2">
                                <span class="bg-blue-500 text-white px-2 py-1 rounded text-xs font-semibold">SEARCHING RIDER</span>
                                <span class="bg-yellow-400 text-white px-2 py-1 rounded text-xs">Package</span>
                            </div>
                            <div class="font-semibold text-lg">Pickup → Kabul University</div>
                            <div class="text-sm text-gray-600">Order #RS-2024-${Math.floor(Math.random() * 1000)}</div>
                        </div>
                        <div class="text-right">
                            <div class="text-lg font-bold text-green-600">67 AFN</div>
                            <div class="text-sm text-gray-600">5.2 km</div>
                        </div>
                    </div>
                    
                    <div class="flex items-center justify-center py-8">
                        <div class="text-center">
                            <div class="w-16 h-16 border-4 border-blue-500 border-t-transparent rounded-full animate-spin mx-auto mb-4"></div>
                            <div class="font-semibold">Finding the best rider for you...</div>
                            <div class="text-sm text-gray-600">This usually takes 1-2 minutes</div>
                        </div>
                    </div>
                    
                    <button onclick="cancelOrder()" class="w-full bg-red-500 text-white py-2 rounded-lg hover:bg-red-600">
                        Cancel Order
                    </button>
                </div>
            `;
            
            // Simulate finding a rider after 3 seconds
            setTimeout(() => {
                activeOrdersContainer.innerHTML = `
                    <div class="border-2 border-green-500 bg-green-50 rounded-lg p-4">
                        <div class="flex justify-between items-start mb-4">
                            <div>
                                <div class="flex items-center space-x-2 mb-2">
                                    <span class="bg-green-500 text-white px-2 py-1 rounded text-xs font-semibold">RIDER FOUND</span>
                                    <span class="bg-yellow-400 text-white px-2 py-1 rounded text-xs">Package</span>
                                </div>
                                <div class="font-semibold text-lg">Pickup → Kabul University</div>
                                <div class="text-sm text-gray-600">Order #RS-2024-${Math.floor(Math.random() * 1000)}</div>
                            </div>
                            <div class="text-right">
                                <div class="text-lg font-bold text-green-600">67 AFN</div>
                                <div class="text-sm text-gray-600">5.2 km</div>
                            </div>
                        </div>
                        
                        <div class="bg-white rounded-lg p-4 mb-4">
                            <div class="flex items-center justify-between">
                                <div class="flex items-center space-x-3">
                                    <div class="w-12 h-12 bg-green-500 rounded-full flex items-center justify-center text-white font-bold">
                                        FA
                                    </div>
                                    <div>
                                        <div class="font-semibold">Farid Ahmad</div>
                                        <div class="text-sm text-gray-600">★ 4.8 • Honda 125</div>
                                        <div class="text-sm text-green-600">Arriving in 3 minutes</div>
                                    </div>
                                </div>
                                <div class="flex space-x-2">
                                    <button class="p-2 bg-green-500 text-white rounded-lg hover:bg-green-600">
                                        <i class="fas fa-phone"></i>
                                    </button>
                                    <button class="p-2 bg-blue-500 text-white rounded-lg hover:bg-blue-600">
                                        <i class="fas fa-comment"></i>
                                    </button>
                                </div>
                            </div>
                        </div>
                        
                        <button onclick="showTrackingModal()" class="w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600">
                            <i class="fas fa-map-marker-alt mr-2"></i>Track Order
                        </button>
                    </div>
                `;
            }, 3000);
            
            alert('Order placed successfully! Searching for a rider...');
        }

        // Cancel order
        function cancelOrder() {
            document.getElementById('active-orders').innerHTML = '';
            document.getElementById('no-active-orders').classList.remove('hidden');
            alert('Order cancelled successfully.');
        }

        // Show tracking modal
        function showTrackingModal() {
            document.getElementById('tracking-modal').classList.remove('hidden');
            document.getElementById('tracking-modal').classList.add('flex');
        }

        // Close tracking modal
        function closeTrackingModal() {
            document.getElementById('tracking-modal').classList.add('hidden');
            document.getElementById('tracking-modal').classList.remove('flex');
        }

        // Rider app functions
        function toggleRiderStatus() {
            const statusBtn = event.target;
            const statusIndicator = document.querySelector('.pulse-dot').parentElement;
            
            if (statusBtn.textContent.trim() === 'Go Offline') {
                statusBtn.textContent = 'Go Online';
                statusBtn.classList.remove('bg-red-500', 'hover:bg-red-600');
                statusBtn.classList.add('bg-green-500', 'hover:bg-green-600');
                statusIndicator.innerHTML = '<div class="w-3 h-3 bg-red-500 rounded-full mr-2"></div><span class="text-red-600 font-semibold">Offline</span>';
            } else {
                statusBtn.textContent = 'Go Offline';
                statusBtn.classList.remove('bg-green-500', 'hover:bg-green-600');
                statusBtn.classList.add('bg-red-500', 'hover:bg-red-600');
                statusIndicator.innerHTML = '<div class="w-3 h-3 bg-green-500 rounded-full pulse-dot mr-2"></div><span class="text-green-600 font-semibold">Online</span>';
            }
        }

        function acceptOrder() {
            // Hide available orders and show current delivery
            document.getElementById('current-deliveries').classList.remove('hidden');
            alert('Order accepted! Navigate to pickup location.');
        }

        // Admin panel functions
        function switchAdminTab(tabName) {
            // Hide all tab contents
            document.querySelectorAll('.admin-tab-content').forEach(content => {
                content.classList.add('hidden');
            });
            
            // Show selected tab content
            document.getElementById('admin-' + tabName).classList.remove('hidden');
            
            // Update tab button states
            document.querySelectorAll('.admin-tab').forEach(tab => {
                tab.classList.remove('border-blue-500', 'text-blue-600');
                tab.classList.add('border-transparent', 'text-gray-500');
            });
            
            document.querySelector(`[data-tab="${tabName}"]`).classList.remove('border-transparent', 'text-gray-500');
            document.querySelector(`[data-tab="${tabName}"]`).classList.add('border-blue-500', 'text-blue-600');
        }

        // Initialize default selections
        document.addEventListener('DOMContentLoaded', function() {
            selectService('package');
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96b82580b60890aa',t:'MTc1NDU4NDEwMC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
