# The First Motorbike Web Application In Afghanistan.

Motobike web application 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RideSwift - Motorbike Delivery Platform</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        .gradient-bg { background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); }
        .card-hover { transition: all 0.3s ease; }
        .card-hover:hover { transform: translateY(-5px); box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1); }
        .animate-pulse-slow { animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite; }
        .map-container { background: linear-gradient(45deg, #e8f5e8, #f0f8f0); }
    </style>
</head>
<body class="bg-gray-50 font-sans">
    <!-- Navigation -->
    <nav class="bg-white shadow-lg fixed w-full top-0 z-50">
        <div class="max-w-7xl mx-auto px-4">
            <div class="flex justify-between items-center py-4">
                <div class="flex items-center space-x-2">
                    <div class="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-600 rounded-lg flex items-center justify-center">
                        <i class="fas fa-motorcycle text-white text-lg"></i>
                    </div>
                    <span class="text-2xl font-bold text-gray-800">RideSwift</span>
                </div>
                <div class="flex items-center space-x-4">
                    <button onclick="showInterface('customer')" class="px-4 py-2 text-blue-600 hover:bg-blue-50 rounded-lg transition-colors">Customer</button>
                    <button onclick="showInterface('rider')" class="px-4 py-2 text-green-600 hover:bg-green-50 rounded-lg transition-colors">Rider</button>
                    <button onclick="showInterface('admin')" class="px-4 py-2 text-purple-600 hover:bg-purple-50 rounded-lg transition-colors">Admin</button>
                    <button onclick="showInterface('home')" class="px-4 py-2 bg-gray-800 text-white rounded-lg hover:bg-gray-700 transition-colors">Home</button>
                </div>
            </div>
        </div>
    </nav>

    <!-- Home Interface -->
    <div id="home-interface" class="interface pt-20">
        <!-- Hero Section -->
        <section class="gradient-bg text-white py-20">
            <div class="max-w-7xl mx-auto px-4 text-center">
                <h1 class="text-5xl font-bold mb-6">Fast, Secure Motorbike Delivery</h1>
                <p class="text-xl mb-8 opacity-90">Connect customers, riders, and businesses with our comprehensive delivery platform</p>
                <div class="flex justify-center space-x-4">
                    <button onclick="showInterface('customer')" class="bg-white text-blue-600 px-8 py-3 rounded-lg font-semibold hover:bg-gray-100 transition-colors">
                        <i class="fas fa-user mr-2"></i>Customer App
                    </button>
                    <button onclick="showInterface('rider')" class="bg-transparent border-2 border-white text-white px-8 py-3 rounded-lg font-semibold hover:bg-white hover:text-blue-600 transition-colors">
                        <i class="fas fa-motorcycle mr-2"></i>Rider App
                    </button>
                </div>
            </div>
        </section>

        <!-- Features Overview -->
        <section class="py-16">
            <div class="max-w-7xl mx-auto px-4">
                <h2 class="text-3xl font-bold text-center mb-12">Platform Features</h2>
                <div class="grid md:grid-cols-3 gap-8">
                    <div class="card-hover bg-white p-6 rounded-xl shadow-lg">
                        <div class="w-12 h-12 bg-blue-100 rounded-lg flex items-center justify-center mb-4">
                            <i class="fas fa-shield-alt text-blue-600 text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Advanced Security</h3>
                        <p class="text-gray-600">2FA authentication, OTP verification, SOS features, and comprehensive identity verification</p>
                    </div>
                    <div class="card-hover bg-white p-6 rounded-xl shadow-lg">
                        <div class="w-12 h-12 bg-green-100 rounded-lg flex items-center justify-center mb-4">
                            <i class="fas fa-map-marked-alt text-green-600 text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Smart Tracking</h3>
                        <p class="text-gray-600">Real-time GPS tracking, optimal route suggestions, and live ETA updates</p>
                    </div>
                    <div class="card-hover bg-white p-6 rounded-xl shadow-lg">
                        <div class="w-12 h-12 bg-purple-100 rounded-lg flex items-center justify-center mb-4">
                            <i class="fas fa-wallet text-purple-600 text-xl"></i>
                        </div>
                        <h3 class="text-xl font-semibold mb-3">Flexible Payments</h3>
                        <p class="text-gray-600">In-app wallet, split payments, subscription plans, and instant payouts</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Customer Interface -->
    <div id="customer-interface" class="interface hidden pt-20">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <!-- Customer Dashboard -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="flex items-center justify-between mb-6">
                    <div class="flex items-center space-x-4">
                        <div class="w-16 h-16 bg-gradient-to-r from-blue-400 to-blue-600 rounded-full flex items-center justify-center">
                            <i class="fas fa-user text-white text-xl"></i>
                        </div>
                        <div>
                            <h2 class="text-2xl font-bold">Welcome, Ahmad Khan</h2>
                            <p class="text-gray-600">Verified Customer • 4.8 ⭐</p>
                        </div>
                    </div>
                    <div class="text-right">
                        <p class="text-sm text-gray-500">Wallet Balance</p>
                        <p class="text-2xl font-bold text-green-600">2,450 AFN</p>
                    </div>
                </div>

                <!-- Quick Actions -->
                <div class="grid md:grid-cols-4 gap-4 mb-8">
                    <button onclick="showCustomerSection('order')" class="p-4 bg-blue-50 rounded-lg hover:bg-blue-100 transition-colors">
                        <i class="fas fa-plus text-blue-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-blue-600">New Order</p>
                    </button>
                    <button onclick="showCustomerSection('tracking')" class="p-4 bg-green-50 rounded-lg hover:bg-green-100 transition-colors">
                        <i class="fas fa-map-marker-alt text-green-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-green-600">Track Order</p>
                    </button>
                    <button onclick="showCustomerSection('history')" class="p-4 bg-purple-50 rounded-lg hover:bg-purple-100 transition-colors">
                        <i class="fas fa-history text-purple-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-purple-600">Order History</p>
                    </button>
                    <button onclick="showCustomerSection('profile')" class="p-4 bg-orange-50 rounded-lg hover:bg-orange-100 transition-colors">
                        <i class="fas fa-user-cog text-orange-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-orange-600">Profile</p>
                    </button>
                </div>
            </div>

            <!-- Order Placement Section -->
            <div id="customer-order" class="customer-section">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-bold mb-6">Place New Order</h3>
                    
                    <!-- Service Type Selection -->
                    <div class="mb-6">
                        <label class="block text-sm font-medium mb-3">Service Type</label>
                        <div class="grid md:grid-cols-2 gap-4">
                            <div class="border-2 border-blue-200 rounded-lg p-4 cursor-pointer hover:border-blue-400 transition-colors" onclick="selectService('package')">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-box text-blue-600 text-xl"></i>
                                    <div>
                                        <h4 class="font-semibold">Package Delivery</h4>
                                        <p class="text-sm text-gray-600">Send packages and documents</p>
                                    </div>
                                </div>
                            </div>
                            <div class="border-2 border-gray-200 rounded-lg p-4 cursor-pointer hover:border-blue-400 transition-colors" onclick="selectService('ride')">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-motorcycle text-gray-600 text-xl"></i>
                                    <div>
                                        <h4 class="font-semibold">Solo Ride</h4>
                                        <p class="text-sm text-gray-600">Personal transportation</p>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Location Selection -->
                    <div class="grid md:grid-cols-2 gap-6 mb-6">
                        <div>
                            <label class="block text-sm font-medium mb-2">Pickup Location</label>
                            <div class="relative">
                                <input type="text" placeholder="Enter pickup address" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <button class="absolute right-3 top-3 text-blue-600 hover:text-blue-800">
                                    <i class="fas fa-map-marker-alt"></i>
                                </button>
                            </div>
                        </div>
                        <div>
                            <label class="block text-sm font-medium mb-2">Drop-off Location</label>
                            <div class="relative">
                                <input type="text" placeholder="Enter destination address" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent">
                                <button class="absolute right-3 top-3 text-blue-600 hover:text-blue-800">
                                    <i class="fas fa-map-marker-alt"></i>
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Map Display -->
                    <div class="map-container h-64 rounded-lg mb-6 flex items-center justify-center">
                        <div class="text-center">
                            <i class="fas fa-map text-4xl text-green-600 mb-2"></i>
                            <p class="text-gray-600">Interactive map will display route here</p>
                        </div>
                    </div>

                    <!-- Package Details -->
                    <div id="package-details" class="mb-6">
                        <h4 class="font-semibold mb-3">Package Details</h4>
                        <div class="grid md:grid-cols-2 gap-4">
                            <input type="text" placeholder="Package description" class="p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                            <select class="p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                                <option>Package Size</option>
                                <option>Small (up to 2kg)</option>
                                <option>Medium (2-5kg)</option>
                                <option>Large (5-10kg)</option>
                            </select>
                        </div>
                        <div class="mt-4">
                            <label class="block text-sm font-medium mb-2">Package Photo (Optional)</label>
                            <div class="border-2 border-dashed border-gray-300 rounded-lg p-6 text-center cursor-pointer hover:border-blue-400 transition-colors">
                                <i class="fas fa-camera text-gray-400 text-2xl mb-2"></i>
                                <p class="text-gray-600">Click to upload package photo</p>
                            </div>
                        </div>
                    </div>

                    <!-- Fare Calculation -->
                    <div class="bg-gray-50 rounded-lg p-4 mb-6">
                        <div class="flex justify-between items-center mb-2">
                            <span>Distance:</span>
                            <span class="font-semibold">8.5 km</span>
                        </div>
                        <div class="flex justify-between items-center mb-2">
                            <span>Base Fare:</span>
                            <span>85 AFN</span>
                        </div>
                        <div class="flex justify-between items-center mb-2">
                            <span>Service Fee:</span>
                            <span>15 AFN</span>
                        </div>
                        <div class="border-t pt-2 flex justify-between items-center font-bold text-lg">
                            <span>Total:</span>
                            <span class="text-green-600">100 AFN</span>
                        </div>
                        <p class="text-sm text-gray-600 mt-2">
                            <i class="fas fa-clock mr-1"></i>
                            Estimated delivery: 25-30 minutes
                        </p>
                    </div>

                    <!-- Payment Method -->
                    <div class="mb-6">
                        <label class="block text-sm font-medium mb-3">Payment Method</label>
                        <div class="space-y-2">
                            <label class="flex items-center space-x-3 p-3 border rounded-lg cursor-pointer hover:bg-gray-50">
                                <input type="radio" name="payment" value="wallet" class="text-blue-600">
                                <i class="fas fa-wallet text-blue-600"></i>
                                <span>Wallet Balance (2,450 AFN)</span>
                            </label>
                            <label class="flex items-center space-x-3 p-3 border rounded-lg cursor-pointer hover:bg-gray-50">
                                <input type="radio" name="payment" value="cash">
                                <i class="fas fa-money-bill text-green-600"></i>
                                <span>Cash on Delivery</span>
                            </label>
                        </div>
                    </div>

                    <!-- Order Button -->
                    <button onclick="placeOrder()" class="w-full bg-blue-600 text-white py-3 rounded-lg font-semibold hover:bg-blue-700 transition-colors">
                        <i class="fas fa-motorcycle mr-2"></i>
                        Place Order
                    </button>
                </div>
            </div>

            <!-- Real-time Tracking Section -->
            <div id="customer-tracking" class="customer-section hidden">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <div class="flex items-center justify-between mb-6">
                        <h3 class="text-xl font-bold">Track Your Order</h3>
                        <div class="flex items-center space-x-2">
                            <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                            <span class="text-green-600 font-semibold">Live Tracking</span>
                        </div>
                    </div>

                    <!-- Order Status -->
                    <div class="bg-blue-50 rounded-lg p-4 mb-6">
                        <div class="flex items-center justify-between mb-3">
                            <div class="flex items-center space-x-3">
                                <div class="w-12 h-12 bg-blue-600 rounded-full flex items-center justify-center">
                                    <i class="fas fa-motorcycle text-white"></i>
                                </div>
                                <div>
                                    <h4 class="font-semibold">Mohammad Ahmadi</h4>
                                    <p class="text-sm text-gray-600">Rider • 4.9 ⭐ • Honda CB150</p>
                                </div>
                            </div>
                            <div class="text-right">
                                <p class="text-sm text-gray-600">ETA</p>
                                <p class="text-xl font-bold text-blue-600">12 min</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-2">
                            <button class="flex-1 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                <i class="fas fa-phone mr-2"></i>Call Rider
                            </button>
                            <button class="flex-1 bg-gray-600 text-white py-2 rounded-lg hover:bg-gray-700 transition-colors">
                                <i class="fas fa-comment mr-2"></i>Chat
                            </button>
                        </div>
                    </div>

                    <!-- Live Map -->
                    <div class="map-container h-80 rounded-lg mb-6 relative">
                        <div class="absolute inset-0 flex items-center justify-center">
                            <div class="text-center">
                                <div class="w-16 h-16 bg-blue-600 rounded-full flex items-center justify-center mb-4 mx-auto animate-pulse-slow">
                                    <i class="fas fa-motorcycle text-white text-2xl"></i>
                                </div>
                                <p class="text-gray-600">Live tracking map with rider location</p>
                                <p class="text-sm text-gray-500 mt-2">Rider is 2.3 km away from pickup</p>
                            </div>
                        </div>
                        <!-- SOS Button -->
                        <button class="absolute top-4 right-4 bg-red-600 text-white p-3 rounded-full hover:bg-red-700 transition-colors">
                            <i class="fas fa-exclamation-triangle"></i>
                        </button>
                    </div>

                    <!-- Delivery Progress -->
                    <div class="space-y-4">
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center">
                                <i class="fas fa-check text-white text-sm"></i>
                            </div>
                            <div class="flex-1">
                                <p class="font-semibold">Order Confirmed</p>
                                <p class="text-sm text-gray-600">2:30 PM</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center">
                                <i class="fas fa-check text-white text-sm"></i>
                            </div>
                            <div class="flex-1">
                                <p class="font-semibold">Rider Assigned</p>
                                <p class="text-sm text-gray-600">2:32 PM</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center animate-pulse">
                                <i class="fas fa-motorcycle text-white text-sm"></i>
                            </div>
                            <div class="flex-1">
                                <p class="font-semibold">En Route to Pickup</p>
                                <p class="text-sm text-gray-600">Current status</p>
                            </div>
                        </div>
                        <div class="flex items-center space-x-4">
                            <div class="w-8 h-8 bg-gray-300 rounded-full flex items-center justify-center">
                                <i class="fas fa-box text-gray-600 text-sm"></i>
                            </div>
                            <div class="flex-1">
                                <p class="font-semibold text-gray-500">Package Pickup</p>
                                <p class="text-sm text-gray-400">Pending</p>
                            </div>
                        </div>
                    </div>

                    <!-- Share Location -->
                    <div class="mt-6 p-4 bg-yellow-50 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-share-alt text-yellow-600"></i>
                            <div class="flex-1">
                                <p class="font-semibold">Share Live Location</p>
                                <p class="text-sm text-gray-600">Let friends/family track your delivery</p>
                            </div>
                            <button class="bg-yellow-600 text-white px-4 py-2 rounded-lg hover:bg-yellow-700 transition-colors">
                                Share
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Order History Section -->
            <div id="customer-history" class="customer-section hidden">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <div class="flex items-center justify-between mb-6">
                        <h3 class="text-xl font-bold">Order History</h3>
                        <div class="flex items-center space-x-2">
                            <span class="text-sm text-gray-600">Total Orders:</span>
                            <span class="font-bold text-blue-600">47</span>
                        </div>
                    </div>

                    <!-- Rewards Summary -->
                    <div class="bg-gradient-to-r from-purple-500 to-pink-500 text-white rounded-lg p-4 mb-6">
                        <div class="flex items-center justify-between">
                            <div>
                                <h4 class="font-semibold">Loyalty Points</h4>
                                <p class="text-2xl font-bold">1,250 pts</p>
                            </div>
                            <div class="text-right">
                                <p class="text-sm opacity-90">Next Reward</p>
                                <p class="font-semibold">Free delivery at 1,500 pts</p>
                            </div>
                        </div>
                    </div>

                    <!-- Order List -->
                    <div class="space-y-4">
                        <div class="border rounded-lg p-4 hover:bg-gray-50 transition-colors">
                            <div class="flex items-center justify-between mb-2">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-green-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-check text-green-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Package Delivery</p>
                                        <p class="text-sm text-gray-600">Shar-e-Naw to Karte-4</p>
                                    </div>
                                </div>
                                <div class="text-right">
                                    <p class="font-semibold">120 AFN</p>
                                    <p class="text-sm text-gray-600">Dec 15, 2023</p>
                                </div>
                            </div>
                            <div class="flex items-center justify-between">
                                <div class="flex items-center space-x-2">
                                    <span class="text-sm text-gray-600">Rider:</span>
                                    <span class="text-sm font-medium">Ahmad Rezai</span>
                                    <div class="flex text-yellow-400">
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                    </div>
                                </div>
                                <button class="text-blue-600 hover:text-blue-800 text-sm">
                                    <i class="fas fa-redo mr-1"></i>Reorder
                                </button>
                            </div>
                        </div>

                        <div class="border rounded-lg p-4 hover:bg-gray-50 transition-colors">
                            <div class="flex items-center justify-between mb-2">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-blue-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-motorcycle text-blue-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Solo Ride</p>
                                        <p class="text-sm text-gray-600">Wazir Akbar Khan to Airport</p>
                                    </div>
                                </div>
                                <div class="text-right">
                                    <p class="font-semibold">200 AFN</p>
                                    <p class="text-sm text-gray-600">Dec 12, 2023</p>
                                </div>
                            </div>
                            <div class="flex items-center justify-between">
                                <div class="flex items-center space-x-2">
                                    <span class="text-sm text-gray-600">Rider:</span>
                                    <span class="text-sm font-medium">Nasir Ahmadi</span>
                                    <div class="flex text-yellow-400">
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="fas fa-star text-xs"></i>
                                        <i class="far fa-star text-xs"></i>
                                    </div>
                                </div>
                                <button class="text-blue-600 hover:text-blue-800 text-sm">
                                    <i class="fas fa-comment mr-1"></i>Review
                                </button>
                            </div>
                        </div>

                        <div class="border rounded-lg p-4 hover:bg-gray-50 transition-colors">
                            <div class="flex items-center justify-between mb-2">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-red-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-times text-red-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Package Delivery</p>
                                        <p class="text-sm text-gray-600">Cancelled - Payment failed</p>
                                    </div>
                                </div>
                                <div class="text-right">
                                    <p class="font-semibold text-red-600">Cancelled</p>
                                    <p class="text-sm text-gray-600">Dec 10, 2023</p>
                                </div>
                            </div>
                            <div class="flex items-center justify-between">
                                <span class="text-sm text-gray-500">Refund processed automatically</span>
                                <button class="text-blue-600 hover:text-blue-800 text-sm">
                                    <i class="fas fa-redo mr-1"></i>Retry Order
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Profile Section -->
            <div id="customer-profile" class="customer-section hidden">
                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Personal Information -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Personal Information</h3>
                        <div class="space-y-4">
                            <div>
                                <label class="block text-sm font-medium mb-2">Full Name</label>
                                <input type="text" value="Ahmad Khan Ahmadi" class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                            </div>
                            <div>
                                <label class="block text-sm font-medium mb-2">Phone Number</label>
                                <div class="flex">
                                    <input type="text" value="+93 700 123 456" class="flex-1 p-3 border border-gray-300 rounded-l-lg focus:ring-2 focus:ring-blue-500">
                                    <button class="bg-green-600 text-white px-4 rounded-r-lg hover:bg-green-700 transition-colors">
                                        <i class="fas fa-check"></i>
                                    </button>
                                </div>
                            </div>
                            <div>
                                <label class="block text-sm font-medium mb-2">National ID (Tazkira)</label>
                                <div class="flex">
                                    <input type="text" value="1234567890123" class="flex-1 p-3 border border-gray-300 rounded-l-lg focus:ring-2 focus:ring-blue-500">
                                    <button class="bg-green-600 text-white px-4 rounded-r-lg hover:bg-green-700 transition-colors">
                                        <i class="fas fa-shield-alt"></i>
                                    </button>
                                </div>
                            </div>
                            <div>
                                <label class="block text-sm font-medium mb-2">Profile Photo</label>
                                <div class="flex items-center space-x-4">
                                    <div class="w-16 h-16 bg-gray-200 rounded-full flex items-center justify-center">
                                        <i class="fas fa-user text-gray-400 text-xl"></i>
                                    </div>
                                    <button class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                        Upload Photo
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Security & Settings -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Security & Settings</h3>
                        <div class="space-y-4">
                            <div class="flex items-center justify-between p-3 bg-green-50 rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-shield-alt text-green-600"></i>
                                    <div>
                                        <p class="font-semibold">Two-Factor Authentication</p>
                                        <p class="text-sm text-gray-600">SMS + OTP verification</p>
                                    </div>
                                </div>
                                <div class="w-6 h-6 bg-green-600 rounded-full flex items-center justify-center">
                                    <i class="fas fa-check text-white text-xs"></i>
                                </div>
                            </div>

                            <div class="flex items-center justify-between p-3 border rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-bell text-blue-600"></i>
                                    <div>
                                        <p class="font-semibold">Push Notifications</p>
                                        <p class="text-sm text-gray-600">Order updates & promotions</p>
                                    </div>
                                </div>
                                <label class="relative inline-flex items-center cursor-pointer">
                                    <input type="checkbox" checked class="sr-only peer">
                                    <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-blue-600"></div>
                                </label>
                            </div>

                            <div class="flex items-center justify-between p-3 border rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <i class="fas fa-map-marker-alt text-purple-600"></i>
                                    <div>
                                        <p class="font-semibold">Location Sharing</p>
                                        <p class="text-sm text-gray-600">Share with emergency contacts</p>
                                    </div>
                                </div>
                                <label class="relative inline-flex items-center cursor-pointer">
                                    <input type="checkbox" checked class="sr-only peer">
                                    <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-blue-600"></div>
                                </label>
                            </div>
                        </div>

                        <!-- Saved Addresses -->
                        <div class="mt-6">
                            <h4 class="font-semibold mb-3">Saved Addresses</h4>
                            <div class="space-y-2">
                                <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <i class="fas fa-home text-blue-600"></i>
                                        <div>
                                            <p class="font-medium">Home</p>
                                            <p class="text-sm text-gray-600">Shar-e-Naw, District 10</p>
                                        </div>
                                    </div>
                                    <button class="text-gray-400 hover:text-red-600">
                                        <i class="fas fa-trash"></i>
                                    </button>
                                </div>
                                <div class="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <i class="fas fa-briefcase text-green-600"></i>
                                        <div>
                                            <p class="font-medium">Office</p>
                                            <p class="text-sm text-gray-600">Wazir Akbar Khan, District 10</p>
                                        </div>
                                    </div>
                                    <button class="text-gray-400 hover:text-red-600">
                                        <i class="fas fa-trash"></i>
                                    </button>
                                </div>
                            </div>
                            <button class="w-full mt-3 p-3 border-2 border-dashed border-gray-300 rounded-lg text-gray-600 hover:border-blue-400 hover:text-blue-600 transition-colors">
                                <i class="fas fa-plus mr-2"></i>Add New Address
                            </button>
                        </div>
                    </div>
                </div>

                <!-- Subscription Plans -->
                <div class="bg-white rounded-xl shadow-lg p-6 mt-6">
                    <h3 class="text-xl font-bold mb-6">Subscription Plans</h3>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="border-2 border-gray-200 rounded-lg p-4">
                            <h4 class="font-bold text-lg mb-2">Basic</h4>
                            <p class="text-3xl font-bold text-blue-600 mb-4">Free</p>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Standard delivery</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Basic tracking</li>
                                <li class="flex items-center"><i class="fas fa-times text-red-600 mr-2"></i>Priority support</li>
                            </ul>
                            <button class="w-full mt-4 py-2 bg-gray-200 text-gray-600 rounded-lg cursor-not-allowed">
                                Current Plan
                            </button>
                        </div>
                        <div class="border-2 border-blue-500 rounded-lg p-4 relative">
                            <div class="absolute -top-3 left-1/2 transform -translate-x-1/2 bg-blue-500 text-white px-3 py-1 rounded-full text-xs">
                                Popular
                            </div>
                            <h4 class="font-bold text-lg mb-2">Premium</h4>
                            <p class="text-3xl font-bold text-blue-600 mb-4">500 AFN<span class="text-sm text-gray-600">/month</span></p>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Priority delivery</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Advanced tracking</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>24/7 support</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Free delivery (orders >1000 AFN)</li>
                            </ul>
                            <button class="w-full mt-4 py-2 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition-colors">
                                Upgrade Now
                            </button>
                        </div>
                        <div class="border-2 border-gray-200 rounded-lg p-4">
                            <h4 class="font-bold text-lg mb-2">Business</h4>
                            <p class="text-3xl font-bold text-blue-600 mb-4">1200 AFN<span class="text-sm text-gray-600">/month</span></p>
                            <ul class="space-y-2 text-sm">
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Bulk deliveries</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>API access</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Dedicated support</li>
                                <li class="flex items-center"><i class="fas fa-check text-green-600 mr-2"></i>Custom pricing</li>
                            </ul>
                            <button class="w-full mt-4 py-2 bg-purple-600 text-white rounded-lg hover:bg-purple-700 transition-colors">
                                Contact Sales
                            </button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Rider Interface -->
    <div id="rider-interface" class="interface hidden pt-20">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <!-- Rider Dashboard -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="flex items-center justify-between mb-6">
                    <div class="flex items-center space-x-4">
                        <div class="w-16 h-16 bg-gradient-to-r from-green-400 to-green-600 rounded-full flex items-center justify-center">
                            <i class="fas fa-motorcycle text-white text-xl"></i>
                        </div>
                        <div>
                            <h2 class="text-2xl font-bold">Mohammad Ahmadi</h2>
                            <p class="text-gray-600">Verified Rider • 4.9 ⭐ • Honda CB150</p>
                        </div>
                    </div>
                    <div class="text-right">
                        <div class="flex items-center space-x-4">
                            <div class="text-center">
                                <p class="text-sm text-gray-500">Today's Earnings</p>
                                <p class="text-2xl font-bold text-green-600">1,250 AFN</p>
                            </div>
                            <label class="relative inline-flex items-center cursor-pointer">
                                <input type="checkbox" checked class="sr-only peer" onchange="toggleOnlineStatus()">
                                <div class="w-14 h-8 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-green-300 rounded-full peer peer-checked:after:translate-x-6 peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-7 after:w-7 after:transition-all peer-checked:bg-green-600"></div>
                                <span class="ml-3 text-sm font-medium text-gray-900">Online</span>
                            </label>
                        </div>
                    </div>
                </div>

                <!-- Quick Stats -->
                <div class="grid md:grid-cols-4 gap-4">
                    <div class="bg-blue-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-box text-blue-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Today's Orders</p>
                                <p class="text-xl font-bold">12</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-green-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-star text-green-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Rating</p>
                                <p class="text-xl font-bold">4.9</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-purple-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-clock text-purple-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Online Time</p>
                                <p class="text-xl font-bold">6h 30m</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-orange-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-route text-orange-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Distance</p>
                                <p class="text-xl font-bold">85 km</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Available Orders -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="flex items-center justify-between mb-6">
                    <h3 class="text-xl font-bold">Available Orders</h3>
                    <div class="flex items-center space-x-2">
                        <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                        <span class="text-green-600 font-semibold">Live Updates</span>
                    </div>
                </div>

                <!-- Order Cards -->
                <div class="space-y-4">
                    <!-- High Priority Order -->
                    <div class="border-2 border-yellow-300 bg-yellow-50 rounded-lg p-4">
                        <div class="flex items-center justify-between mb-3">
                            <div class="flex items-center space-x-2">
                                <span class="bg-yellow-500 text-white px-2 py-1 rounded-full text-xs font-bold">HIGH PRIORITY</span>
                                <span class="text-sm text-gray-600">Package Delivery</span>
                            </div>
                            <div class="text-right">
                                <p class="text-lg font-bold text-green-600">180 AFN</p>
                                <p class="text-sm text-gray-600">3.2 km • 15 min</p>
                            </div>
                        </div>
                        <div class="grid md:grid-cols-2 gap-4 mb-4">
                            <div>
                                <p class="text-sm text-gray-600">Pickup</p>
                                <p class="font-semibold">Shar-e-Naw Market</p>
                                <p class="text-sm text-gray-500">Customer: Ahmad Khan • 4.8⭐</p>
                            </div>
                            <div>
                                <p class="text-sm text-gray-600">Drop-off</p>
                                <p class="font-semibold">Karte-4 Residential</p>
                                <p class="text-sm text-gray-500">Small package • Fragile</p>
                            </div>
                        </div>
                        <div class="flex space-x-3">
                            <button onclick="acceptOrder()" class="flex-1 bg-green-600 text-white py-2 rounded-lg hover:bg-green-700 transition-colors">
                                <i class="fas fa-check mr-2"></i>Accept Order
                            </button>
                            <button class="px-4 bg-gray-200 text-gray-600 rounded-lg hover:bg-gray-300 transition-colors">
                                <i class="fas fa-times"></i>
                            </button>
                        </div>
                    </div>

                    <!-- Regular Orders -->
                    <div class="border rounded-lg p-4 hover:bg-gray-50 transition-colors">
                        <div class="flex items-center justify-between mb-3">
                            <span class="text-sm text-gray-600">Solo Ride</span>
                            <div class="text-right">
                                <p class="text-lg font-bold text-green-600">120 AFN</p>
                                <p class="text-sm text-gray-600">2.8 km • 12 min</p>
                            </div>
                        </div>
                        <div class="grid md:grid-cols-2 gap-4 mb-4">
                            <div>
                                <p class="text-sm text-gray-600">Pickup</p>
                                <p class="font-semibold">Wazir Akbar Khan</p>
                                <p class="text-sm text-gray-500">Customer: Fatima Ali • 4.6⭐</p>
                            </div>
                            <div>
                                <p class="text-sm text-gray-600">Drop-off</p>
                                <p class="font-semibold">Kabul University</p>
                                <p class="text-sm text-gray-500">1 passenger</p>
                            </div>
                        </div>
                        <div class="flex space-x-3">
                            <button class="flex-1 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                <i class="fas fa-check mr-2"></i>Accept Order
                            </button>
                            <button class="px-4 bg-gray-200 text-gray-600 rounded-lg hover:bg-gray-300 transition-colors">
                                <i class="fas fa-times"></i>
                            </button>
                        </div>
                    </div>

                    <div class="border rounded-lg p-4 hover:bg-gray-50 transition-colors">
                        <div class="flex items-center justify-between mb-3">
                            <span class="text-sm text-gray-600">Package Delivery</span>
                            <div class="text-right">
                                <p class="text-lg font-bold text-green-600">95 AFN</p>
                                <p class="text-sm text-gray-600">1.5 km • 8 min</p>
                            </div>
                        </div>
                        <div class="grid md:grid-cols-2 gap-4 mb-4">
                            <div>
                                <p class="text-sm text-gray-600">Pickup</p>
                                <p class="font-semibold">Chicken Street</p>
                                <p class="text-sm text-gray-500">Customer: Omar Hassan • 4.9⭐</p>
                            </div>
                            <div>
                                <p class="text-sm text-gray-600">Drop-off</p>
                                <p class="font-semibold">Taimani Square</p>
                                <p class="text-sm text-gray-500">Documents • Urgent</p>
                            </div>
                        </div>
                        <div class="flex space-x-3">
                            <button class="flex-1 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                <i class="fas fa-check mr-2"></i>Accept Order
                            </button>
                            <button class="px-4 bg-gray-200 text-gray-600 rounded-lg hover:bg-gray-300 transition-colors">
                                <i class="fas fa-times"></i>
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Active Delivery -->
            <div id="active-delivery" class="bg-white rounded-xl shadow-lg p-6 mb-8 hidden">
                <div class="flex items-center justify-between mb-6">
                    <h3 class="text-xl font-bold">Active Delivery</h3>
                    <div class="flex items-center space-x-2">
                        <div class="w-3 h-3 bg-blue-500 rounded-full animate-pulse"></div>
                        <span class="text-blue-600 font-semibold">In Progress</span>
                    </div>
                </div>

                <!-- Customer Info -->
                <div class="bg-blue-50 rounded-lg p-4 mb-6">
                    <div class="flex items-center justify-between mb-3">
                        <div class="flex items-center space-x-3">
                            <div class="w-12 h-12 bg-blue-600 rounded-full flex items-center justify-center">
                                <i class="fas fa-user text-white"></i>
                            </div>
                            <div>
                                <h4 class="font-semibold">Ahmad Khan</h4>
                                <p class="text-sm text-gray-600">Customer • 4.8 ⭐</p>
                            </div>
                        </div>
                        <div class="text-right">
                            <p class="text-sm text-gray-600">Earnings</p>
                            <p class="text-xl font-bold text-green-600">180 AFN</p>
                        </div>
                    </div>
                    <div class="flex space-x-2">
                        <button class="flex-1 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                            <i class="fas fa-phone mr-2"></i>Call Customer
                        </button>
                        <button class="flex-1 bg-gray-600 text-white py-2 rounded-lg hover:bg-gray-700 transition-colors">
                            <i class="fas fa-comment mr-2"></i>Chat
                        </button>
                    </div>
                </div>

                <!-- Navigation -->
                <div class="map-container h-64 rounded-lg mb-6 relative">
                    <div class="absolute inset-0 flex items-center justify-center">
                        <div class="text-center">
                            <i class="fas fa-route text-4xl text-blue-600 mb-2"></i>
                            <p class="text-gray-600">Smart navigation with optimal route</p>
                            <p class="text-sm text-gray-500 mt-2">Next: Turn right in 200m</p>
                        </div>
                    </div>
                    <!-- Navigation Controls -->
                    <div class="absolute top-4 left-4 space-y-2">
                        <button class="bg-white p-2 rounded-lg shadow-lg hover:bg-gray-50">
                            <i class="fas fa-route text-blue-600"></i>
                        </button>
                        <button class="bg-white p-2 rounded-lg shadow-lg hover:bg-gray-50">
                            <i class="fas fa-traffic-light text-orange-600"></i>
                        </button>
                    </div>
                    <!-- SOS Button -->
                    <button class="absolute top-4 right-4 bg-red-600 text-white p-3 rounded-full hover:bg-red-700 transition-colors">
                        <i class="fas fa-exclamation-triangle"></i>
                    </button>
                </div>

                <!-- Delivery Steps -->
                <div class="space-y-4 mb-6">
                    <div class="flex items-center space-x-4">
                        <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center">
                            <i class="fas fa-check text-white text-sm"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-semibold">Order Accepted</p>
                            <p class="text-sm text-gray-600">3:15 PM</p>
                        </div>
                    </div>
                    <div class="flex items-center space-x-4">
                        <div class="w-8 h-8 bg-blue-500 rounded-full flex items-center justify-center animate-pulse">
                            <i class="fas fa-motorcycle text-white text-sm"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-semibold">En Route to Pickup</p>
                            <p class="text-sm text-gray-600">ETA: 5 minutes</p>
                        </div>
                    </div>
                    <div class="flex items-center space-x-4">
                        <div class="w-8 h-8 bg-gray-300 rounded-full flex items-center justify-center">
                            <i class="fas fa-box text-gray-600 text-sm"></i>
                        </div>
                        <div class="flex-1">
                            <p class="font-semibold text-gray-500">Package Pickup</p>
                            <p class="text-sm text-gray-400">Pending</p>
                        </div>
                    </div>
                </div>

                <!-- Action Buttons -->
                <div class="grid md:grid-cols-2 gap-4">
                    <button class="bg-green-600 text-white py-3 rounded-lg hover:bg-green-700 transition-colors">
                        <i class="fas fa-qrcode mr-2"></i>Scan Pickup QR
                    </button>
                    <button class="bg-orange-600 text-white py-3 rounded-lg hover:bg-orange-700 transition-colors">
                        <i class="fas fa-camera mr-2"></i>Take Photo
                    </button>
                </div>
            </div>

            <!-- Earnings & Finances -->
            <div class="grid md:grid-cols-2 gap-6">
                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-bold mb-6">Earnings Overview</h3>
                    <div class="space-y-4">
                        <div class="flex justify-between items-center p-3 bg-green-50 rounded-lg">
                            <span class="font-semibold">Today</span>
                            <span class="text-xl font-bold text-green-600">1,250 AFN</span>
                        </div>
                        <div class="flex justify-between items-center p-3 bg-blue-50 rounded-lg">
                            <span class="font-semibold">This Week</span>
                            <span class="text-xl font-bold text-blue-600">8,750 AFN</span>
                        </div>
                        <div class="flex justify-between items-center p-3 bg-purple-50 rounded-lg">
                            <span class="font-semibold">This Month</span>
                            <span class="text-xl font-bold text-purple-600">32,400 AFN</span>
                        </div>
                    </div>

                    <!-- Payout Options -->
                    <div class="mt-6">
                        <h4 class="font-semibold mb-3">Request Payout</h4>
                        <div class="space-y-2">
                            <button class="w-full p-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700 transition-colors">
                                <i class="fas fa-bolt mr-2"></i>Instant Payout (5% fee)
                            </button>
                            <button class="w-full p-3 bg-green-600 text-white rounded-lg hover:bg-green-700 transition-colors">
                                <i class="fas fa-calendar mr-2"></i>Weekly Payout (Free)
                            </button>
                        </div>
                    </div>
                </div>

                <div class="bg-white rounded-xl shadow-lg p-6">
                    <h3 class="text-xl font-bold mb-6">Performance Metrics</h3>
                    <div class="space-y-4">
                        <div class="flex justify-between items-center">
                            <span>Acceptance Rate</span>
                            <div class="flex items-center space-x-2">
                                <div class="w-20 bg-gray-200 rounded-full h-2">
                                    <div class="bg-green-600 h-2 rounded-full" style="width: 92%"></div>
                                </div>
                                <span class="font-bold text-green-600">92%</span>
                            </div>
                        </div>
                        <div class="flex justify-between items-center">
                            <span>On-time Delivery</span>
                            <div class="flex items-center space-x-2">
                                <div class="w-20 bg-gray-200 rounded-full h-2">
                                    <div class="bg-blue-600 h-2 rounded-full" style="width: 96%"></div>
                                </div>
                                <span class="font-bold text-blue-600">96%</span>
                            </div>
                        </div>
                        <div class="flex justify-between items-center">
                            <span>Customer Rating</span>
                            <div class="flex items-center space-x-2">
                                <div class="flex text-yellow-400">
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                    <i class="fas fa-star"></i>
                                </div>
                                <span class="font-bold">4.9</span>
                            </div>
                        </div>
                    </div>

                    <!-- Penalties & Bonuses -->
                    <div class="mt-6">
                        <h4 class="font-semibold mb-3">Recent Activity</h4>
                        <div class="space-y-2">
                            <div class="flex justify-between items-center p-2 bg-green-50 rounded">
                                <span class="text-sm">On-time bonus</span>
                                <span class="text-green-600 font-semibold">+25 AFN</span>
                            </div>
                            <div class="flex justify-between items-center p-2 bg-red-50 rounded">
                                <span class="text-sm">Late delivery penalty</span>
                                <span class="text-red-600 font-semibold">-15 AFN</span>
                            </div>
                            <div class="flex justify-between items-center p-2 bg-blue-50 rounded">
                                <span class="text-sm">High rating bonus</span>
                                <span class="text-blue-600 font-semibold">+50 AFN</span>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Admin Interface -->
    <div id="admin-interface" class="interface hidden pt-20">
        <div class="max-w-7xl mx-auto px-4 py-8">
            <!-- Admin Dashboard -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="flex items-center justify-between mb-6">
                    <div>
                        <h2 class="text-2xl font-bold">Admin Dashboard</h2>
                        <p class="text-gray-600">RideSwift Management Portal</p>
                    </div>
                    <div class="flex items-center space-x-4">
                        <div class="text-center">
                            <p class="text-sm text-gray-500">Total Revenue</p>
                            <p class="text-2xl font-bold text-green-600">125,450 AFN</p>
                        </div>
                        <div class="text-center">
                            <p class="text-sm text-gray-500">Active Orders</p>
                            <p class="text-2xl font-bold text-blue-600">47</p>
                        </div>
                    </div>
                </div>

                <!-- Quick Stats -->
                <div class="grid md:grid-cols-5 gap-4">
                    <div class="bg-blue-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-users text-blue-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Total Users</p>
                                <p class="text-xl font-bold">2,847</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-green-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-motorcycle text-green-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Active Riders</p>
                                <p class="text-xl font-bold">156</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-purple-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-store text-purple-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Partner Stores</p>
                                <p class="text-xl font-bold">89</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-orange-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-box text-orange-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Today's Orders</p>
                                <p class="text-xl font-bold">234</p>
                            </div>
                        </div>
                    </div>
                    <div class="bg-red-50 p-4 rounded-lg">
                        <div class="flex items-center space-x-3">
                            <i class="fas fa-exclamation-triangle text-red-600 text-xl"></i>
                            <div>
                                <p class="text-sm text-gray-600">Pending Issues</p>
                                <p class="text-xl font-bold">12</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Admin Navigation -->
            <div class="bg-white rounded-xl shadow-lg p-6 mb-8">
                <div class="grid md:grid-cols-4 gap-4">
                    <button onclick="showAdminSection('users')" class="p-4 bg-blue-50 rounded-lg hover:bg-blue-100 transition-colors">
                        <i class="fas fa-users text-blue-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-blue-600">User Management</p>
                    </button>
                    <button onclick="showAdminSection('finance')" class="p-4 bg-green-50 rounded-lg hover:bg-green-100 transition-colors">
                        <i class="fas fa-chart-line text-green-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-green-600">Financial Management</p>
                    </button>
                    <button onclick="showAdminSection('support')" class="p-4 bg-purple-50 rounded-lg hover:bg-purple-100 transition-colors">
                        <i class="fas fa-headset text-purple-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-purple-600">Support Center</p>
                    </button>
                    <button onclick="showAdminSection('analytics')" class="p-4 bg-orange-50 rounded-lg hover:bg-orange-100 transition-colors">
                        <i class="fas fa-analytics text-orange-600 text-2xl mb-2"></i>
                        <p class="font-semibold text-orange-600">Analytics</p>
                    </button>
                </div>
            </div>

            <!-- User Management Section -->
            <div id="admin-users" class="admin-section">
                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Rider Verification -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Rider Verification Queue</h3>
                        <div class="space-y-4">
                            <div class="border rounded-lg p-4">
                                <div class="flex items-center justify-between mb-3">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-12 h-12 bg-gray-200 rounded-full flex items-center justify-center">
                                            <i class="fas fa-user text-gray-600"></i>
                                        </div>
                                        <div>
                                            <h4 class="font-semibold">Nasir Ahmadi</h4>
                                            <p class="text-sm text-gray-600">Applied 2 hours ago</p>
                                        </div>
                                    </div>
                                    <span class="bg-yellow-100 text-yellow-800 px-2 py-1 rounded-full text-xs">Pending</span>
                                </div>
                                <div class="grid grid-cols-2 gap-2 mb-3 text-sm">
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-id-card text-green-600"></i>
                                        <span>National ID: Verified</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-motorcycle text-blue-600"></i>
                                        <span>Bike Papers: Submitted</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-camera text-purple-600"></i>
                                        <span>Face Recognition: Pending</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-shield-alt text-orange-600"></i>
                                        <span>Background Check: In Progress</span>
                                    </div>
                                </div>
                                <div class="flex space-x-2">
                                    <button class="flex-1 bg-green-600 text-white py-2 rounded-lg hover:bg-green-700 transition-colors">
                                        <i class="fas fa-check mr-2"></i>Approve
                                    </button>
                                    <button class="flex-1 bg-red-600 text-white py-2 rounded-lg hover:bg-red-700 transition-colors">
                                        <i class="fas fa-times mr-2"></i>Reject
                                    </button>
                                    <button class="px-4 bg-gray-200 text-gray-600 rounded-lg hover:bg-gray-300 transition-colors">
                                        <i class="fas fa-eye"></i>
                                    </button>
                                </div>
                            </div>

                            <div class="border rounded-lg p-4">
                                <div class="flex items-center justify-between mb-3">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-12 h-12 bg-gray-200 rounded-full flex items-center justify-center">
                                            <i class="fas fa-user text-gray-600"></i>
                                        </div>
                                        <div>
                                            <h4 class="font-semibold">Farid Hassan</h4>
                                            <p class="text-sm text-gray-600">Applied 5 hours ago</p>
                                        </div>
                                    </div>
                                    <span class="bg-red-100 text-red-800 px-2 py-1 rounded-full text-xs">Issues Found</span>
                                </div>
                                <div class="grid grid-cols-2 gap-2 mb-3 text-sm">
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-id-card text-green-600"></i>
                                        <span>National ID: Verified</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-motorcycle text-red-600"></i>
                                        <span>Bike Papers: Invalid</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-camera text-green-600"></i>
                                        <span>Face Recognition: Passed</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <i class="fas fa-shield-alt text-red-600"></i>
                                        <span>Background Check: Failed</span>
                                    </div>
                                </div>
                                <div class="flex space-x-2">
                                    <button class="flex-1 bg-yellow-600 text-white py-2 rounded-lg hover:bg-yellow-700 transition-colors">
                                        <i class="fas fa-comment mr-2"></i>Request Resubmission
                                    </button>
                                    <button class="flex-1 bg-red-600 text-white py-2 rounded-lg hover:bg-red-700 transition-colors">
                                        <i class="fas fa-ban mr-2"></i>Reject
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- User Management -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">User Management</h3>
                        
                        <!-- Search and Filters -->
                        <div class="mb-4">
                            <div class="flex space-x-2">
                                <input type="text" placeholder="Search users..." class="flex-1 p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                                <select class="p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                                    <option>All Users</option>
                                    <option>Customers</option>
                                    <option>Riders</option>
                                    <option>Stores</option>
                                </select>
                            </div>
                        </div>

                        <!-- User List -->
                        <div class="space-y-3">
                            <div class="flex items-center justify-between p-3 border rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-blue-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-user text-blue-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Ahmad Khan</p>
                                        <p class="text-sm text-gray-600">Customer • 4.8⭐ • 47 orders</p>
                                    </div>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="bg-green-100 text-green-800 px-2 py-1 rounded-full text-xs">Active</span>
                                    <button class="text-gray-400 hover:text-blue-600">
                                        <i class="fas fa-edit"></i>
                                    </button>
                                </div>
                            </div>

                            <div class="flex items-center justify-between p-3 border rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-green-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-motorcycle text-green-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Mohammad Ahmadi</p>
                                        <p class="text-sm text-gray-600">Rider • 4.9⭐ • 234 deliveries</p>
                                    </div>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="bg-green-100 text-green-800 px-2 py-1 rounded-full text-xs">Online</span>
                                    <button class="text-gray-400 hover:text-blue-600">
                                        <i class="fas fa-edit"></i>
                                    </button>
                                </div>
                            </div>

                            <div class="flex items-center justify-between p-3 border rounded-lg">
                                <div class="flex items-center space-x-3">
                                    <div class="w-10 h-10 bg-red-100 rounded-full flex items-center justify-center">
                                        <i class="fas fa-user text-red-600"></i>
                                    </div>
                                    <div>
                                        <p class="font-semibold">Fatima Ali</p>
                                        <p class="text-sm text-gray-600">Customer • 3.2⭐ • 12 complaints</p>
                                    </div>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <span class="bg-red-100 text-red-800 px-2 py-1 rounded-full text-xs">Flagged</span>
                                    <button class="text-gray-400 hover:text-red-600">
                                        <i class="fas fa-ban"></i>
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Automated Alerts -->
                        <div class="mt-6 p-4 bg-yellow-50 rounded-lg">
                            <h4 class="font-semibold mb-2">Automated Alerts</h4>
                            <div class="space-y-2 text-sm">
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-exclamation-triangle text-yellow-600"></i>
                                    <span>3 riders with rating below 4.0</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-flag text-red-600"></i>
                                    <span>5 customers with multiple complaints</span>
                                </div>
                                <div class="flex items-center space-x-2">
                                    <i class="fas fa-clock text-blue-600"></i>
                                    <span>12 pending verifications over 24 hours</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Financial Management Section -->
            <div id="admin-finance" class="admin-section hidden">
                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Revenue Overview -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Revenue Overview</h3>
                        <div class="space-y-4">
                            <div class="flex justify-between items-center p-4 bg-green-50 rounded-lg">
                                <div>
                                    <p class="text-sm text-gray-600">Today's Revenue</p>
                                    <p class="text-2xl font-bold text-green-600">12,450 AFN</p>
                                </div>
                                <i class="fas fa-arrow-up text-green-600 text-xl"></i>
                            </div>
                            <div class="flex justify-between items-center p-4 bg-blue-50 rounded-lg">
                                <div>
                                    <p class="text-sm text-gray-600">This Week</p>
                                    <p class="text-2xl font-bold text-blue-600">87,650 AFN</p>
                                </div>
                                <i class="fas fa-chart-line text-blue-600 text-xl"></i>
                            </div>
                            <div class="flex justify-between items-center p-4 bg-purple-50 rounded-lg">
                                <div>
                                    <p class="text-sm text-gray-600">This Month</p>
                                    <p class="text-2xl font-bold text-purple-600">345,200 AFN</p>
                                </div>
                                <i class="fas fa-calendar text-purple-600 text-xl"></i>
                            </div>
                        </div>

                        <!-- Commission Breakdown -->
                        <div class="mt-6">
                            <h4 class="font-semibold mb-3">Commission Breakdown</h4>
                            <div class="space-y-2">
                                <div class="flex justify-between items-center">
                                    <span class="text-sm">Store Commissions (15-20%)</span>
                                    <span class="font-semibold">45,600 AFN</span>
                                </div>
                                <div class="flex justify-between items-center">
                                    <span class="text-sm">Service Fees</span>
                                    <span class="font-semibold">23,400 AFN</span>
                                </div>
                                <div class="flex justify-between items-center">
                                    <span class="text-sm">Subscription Revenue</span>
                                    <span class="font-semibold">15,800 AFN</span>
                                </div>
                                <div class="flex justify-between items-center">
                                    <span class="text-sm">Advertisement Revenue</span>
                                    <span class="font-semibold">8,200 AFN</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Payout Management -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Payout Management</h3>
                        
                        <!-- Pending Payouts -->
                        <div class="mb-6">
                            <h4 class="font-semibold mb-3">Pending Payouts</h4>
                            <div class="space-y-3">
                                <div class="flex items-center justify-between p-3 border rounded-lg">
                                    <div>
                                        <p class="font-semibold">Mohammad Ahmadi</p>
                                        <p class="text-sm text-gray-600">Rider • Instant Payout</p>
                                    </div>
                                    <div class="text-right">
                                        <p class="font-bold">1,250 AFN</p>
                                        <p class="text-sm text-gray-600">Fee: 62.5 AFN</p>
                                    </div>
                                    <button class="bg-green-600 text-white px-3 py-1 rounded hover:bg-green-700 transition-colors">
                                        Process
                                    </button>
                                </div>
                                <div class="flex items-center justify-between p-3 border rounded-lg">
                                    <div>
                                        <p class="font-semibold">Kabul Restaurant</p>
                                        <p class="text-sm text-gray-600">Store • Daily Settlement</p>
                                    </div>
                                    <div class="text-right">
                                        <p class="font-bold">8,750 AFN</p>
                                        <p class="text-sm text-gray-600">Commission: 1,750 AFN</p>
                                    </div>
                                    <button class="bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700 transition-colors">
                                        Process
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Auto Settlement Settings -->
                        <div class="p-4 bg-gray-50 rounded-lg">
                            <h4 class="font-semibold mb-3">Auto Settlement Settings</h4>
                            <div class="space-y-3">
                                <div class="flex items-center justify-between">
                                    <span class="text-sm">Store Daily Settlements</span>
                                    <label class="relative inline-flex items-center cursor-pointer">
                                        <input type="checkbox" checked class="sr-only peer">
                                        <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-blue-600"></div>
                                    </label>
                                </div>
                                <div class="flex items-center justify-between">
                                    <span class="text-sm">Rider Weekly Payouts</span>
                                    <label class="relative inline-flex items-center cursor-pointer">
                                        <input type="checkbox" checked class="sr-only peer">
                                        <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-4 peer-focus:ring-blue-300 rounded-full peer peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all peer-checked:bg-blue-600"></div>
                                    </label>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Advanced Analytics -->
                <div class="bg-white rounded-xl shadow-lg p-6 mt-6">
                    <h3 class="text-xl font-bold mb-6">Advanced Analytics</h3>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="text-center">
                            <div class="w-24 h-24 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-chart-pie text-blue-600 text-2xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Revenue Distribution</h4>
                            <p class="text-sm text-gray-600">Breakdown by service type and commission structure</p>
                        </div>
                        <div class="text-center">
                            <div class="w-24 h-24 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-trending-up text-green-600 text-2xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Growth Metrics</h4>
                            <p class="text-sm text-gray-600">User acquisition, retention, and revenue growth</p>
                        </div>
                        <div class="text-center">
                            <div class="w-24 h-24 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-map-marked-alt text-purple-600 text-2xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Geographic Analysis</h4>
                            <p class="text-sm text-gray-600">High-demand areas and optimization opportunities</p>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Support Center Section -->
            <div id="admin-support" class="admin-section hidden">
                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Ticket Management -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Support Tickets</h3>
                        
                        <!-- Ticket Stats -->
                        <div class="grid grid-cols-3 gap-4 mb-6">
                            <div class="text-center p-3 bg-red-50 rounded-lg">
                                <p class="text-2xl font-bold text-red-600">12</p>
                                <p class="text-sm text-gray-600">Urgent</p>
                            </div>
                            <div class="text-center p-3 bg-yellow-50 rounded-lg">
                                <p class="text-2xl font-bold text-yellow-600">28</p>
                                <p class="text-sm text-gray-600">Open</p>
                            </div>
                            <div class="text-center p-3 bg-green-50 rounded-lg">
                                <p class="text-2xl font-bold text-green-600">156</p>
                                <p class="text-sm text-gray-600">Resolved</p>
                            </div>
                        </div>

                        <!-- Ticket List -->
                        <div class="space-y-3">
                            <div class="border-l-4 border-red-500 bg-red-50 p-4 rounded-r-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="font-semibold">Payment Issue</span>
                                    <span class="bg-red-100 text-red-800 px-2 py-1 rounded-full text-xs">Urgent</span>
                                </div>
                                <p class="text-sm text-gray-600 mb-2">Customer unable to complete payment for order #12345</p>
                                <div class="flex items-center justify-between text-sm">
                                    <span class="text-gray-500">Ahmad Khan • 2 hours ago</span>
                                    <button class="text-blue-600 hover:text-blue-800">Respond</button>
                                </div>
                            </div>

                            <div class="border-l-4 border-yellow-500 bg-yellow-50 p-4 rounded-r-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="font-semibold">Rider Complaint</span>
                                    <span class="bg-yellow-100 text-yellow-800 px-2 py-1 rounded-full text-xs">Medium</span>
                                </div>
                                <p class="text-sm text-gray-600 mb-2">Customer reports rude behavior from rider</p>
                                <div class="flex items-center justify-between text-sm">
                                    <span class="text-gray-500">Fatima Ali • 4 hours ago</span>
                                    <button class="text-blue-600 hover:text-blue-800">Investigate</button>
                                </div>
                            </div>

                            <div class="border-l-4 border-blue-500 bg-blue-50 p-4 rounded-r-lg">
                                <div class="flex items-center justify-between mb-2">
                                    <span class="font-semibold">App Bug Report</span>
                                    <span class="bg-blue-100 text-blue-800 px-2 py-1 rounded-full text-xs">Low</span>
                                </div>
                                <p class="text-sm text-gray-600 mb-2">GPS tracking not working properly on Android</p>
                                <div class="flex items-center justify-between text-sm">
                                    <span class="text-gray-500">Mohammad Ahmadi • 6 hours ago</span>
                                    <button class="text-blue-600 hover:text-blue-800">Forward to Tech</button>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Live Chat Support -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Live Chat Support</h3>
                        
                        <!-- Active Chats -->
                        <div class="mb-6">
                            <h4 class="font-semibold mb-3">Active Chats (3)</h4>
                            <div class="space-y-3">
                                <div class="flex items-center justify-between p-3 bg-green-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-3 h-3 bg-green-500 rounded-full"></div>
                                        <div>
                                            <p class="font-semibold">Ahmad Khan</p>
                                            <p class="text-sm text-gray-600">Order tracking issue</p>
                                        </div>
                                    </div>
                                    <button class="bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700 transition-colors">
                                        Join
                                    </button>
                                </div>
                                <div class="flex items-center justify-between p-3 bg-yellow-50 rounded-lg">
                                    <div class="flex items-center space-x-3">
                                        <div class="w-3 h-3 bg-yellow-500 rounded-full"></div>
                                        <div>
                                            <p class="font-semibold">Mohammad Ahmadi</p>
                                            <p class="text-sm text-gray-600">Payout question</p>
                                        </div>
                                    </div>
                                    <button class="bg-blue-600 text-white px-3 py-1 rounded hover:bg-blue-700 transition-colors">
                                        Join
                                    </button>
                                </div>
                            </div>
                        </div>

                        <!-- Chat Interface -->
                        <div class="border rounded-lg h-64 flex flex-col">
                            <div class="bg-gray-50 p-3 border-b">
                                <p class="font-semibold">Chat with Ahmad Khan</p>
                                <p class="text-sm text-gray-600">Customer • Order #12345</p>
                            </div>
                            <div class="flex-1 p-3 overflow-y-auto">
                                <div class="space-y-3">
                                    <div class="flex">
                                        <div class="bg-gray-200 rounded-lg p-2 max-w-xs">
                                            <p class="text-sm">Hi, I can't see my rider's location on the map</p>
                                        </div>
                                    </div>
                                    <div class="flex justify-end">
                                        <div class="bg-blue-600 text-white rounded-lg p-2 max-w-xs">
                                            <p class="text-sm">Let me check that for you. Can you please refresh the app?</p>
                                        </div>
                                    </div>
                                    <div class="flex">
                                        <div class="bg-gray-200 rounded-lg p-2 max-w-xs">
                                            <p class="text-sm">I tried that but it's still not working</p>
                                        </div>
                                    </div>
                                </div>
                            </div>
                            <div class="border-t p-3">
                                <div class="flex space-x-2">
                                    <input type="text" placeholder="Type your message..." class="flex-1 p-2 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                                    <button class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                        Send
                                    </button>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Complaint Handling -->
                <div class="bg-white rounded-xl shadow-lg p-6 mt-6">
                    <h3 class="text-xl font-bold mb-6">Complaint Management</h3>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="border rounded-lg p-4">
                            <div class="flex items-center justify-between mb-3">
                                <h4 class="font-semibold">Delivery Issues</h4>
                                <span class="bg-red-100 text-red-800 px-2 py-1 rounded-full text-xs">8 Active</span>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li>• Late delivery complaints</li>
                                <li>• Package damage reports</li>
                                <li>• Wrong delivery address</li>
                                <li>• Missing items</li>
                            </ul>
                            <button class="w-full mt-3 bg-red-600 text-white py-2 rounded-lg hover:bg-red-700 transition-colors">
                                Review All
                            </button>
                        </div>
                        <div class="border rounded-lg p-4">
                            <div class="flex items-center justify-between mb-3">
                                <h4 class="font-semibold">Rider Behavior</h4>
                                <span class="bg-yellow-100 text-yellow-800 px-2 py-1 rounded-full text-xs">5 Active</span>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li>• Unprofessional conduct</li>
                                <li>• Safety violations</li>
                                <li>• Communication issues</li>
                                <li>• Route deviations</li>
                            </ul>
                            <button class="w-full mt-3 bg-yellow-600 text-white py-2 rounded-lg hover:bg-yellow-700 transition-colors">
                                Investigate
                            </button>
                        </div>
                        <div class="border rounded-lg p-4">
                            <div class="flex items-center justify-between mb-3">
                                <h4 class="font-semibold">Payment Disputes</h4>
                                <span class="bg-blue-100 text-blue-800 px-2 py-1 rounded-full text-xs">3 Active</span>
                            </div>
                            <ul class="space-y-2 text-sm">
                                <li>• Overcharging claims</li>
                                <li>• Failed transactions</li>
                                <li>• Refund requests</li>
                                <li>• Commission disputes</li>
                            </ul>
                            <button class="w-full mt-3 bg-blue-600 text-white py-2 rounded-lg hover:bg-blue-700 transition-colors">
                                Process
                            </button>
                        </div>
                    </div>
                </div>
            </div>

            <!-- Analytics Section -->
            <div id="admin-analytics" class="admin-section hidden">
                <div class="grid md:grid-cols-2 gap-6">
                    <!-- Performance Metrics -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">Performance Metrics</h3>
                        <div class="space-y-6">
                            <div>
                                <div class="flex justify-between items-center mb-2">
                                    <span class="text-sm font-medium">Order Completion Rate</span>
                                    <span class="text-sm font-bold">94.2%</span>
                                </div>
                                <div class="w-full bg-gray-200 rounded-full h-2">
                                    <div class="bg-green-600 h-2 rounded-full" style="width: 94.2%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between items-center mb-2">
                                    <span class="text-sm font-medium">Average Delivery Time</span>
                                    <span class="text-sm font-bold">23 min</span>
                                </div>
                                <div class="w-full bg-gray-200 rounded-full h-2">
                                    <div class="bg-blue-600 h-2 rounded-full" style="width: 76%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between items-center mb-2">
                                    <span class="text-sm font-medium">Customer Satisfaction</span>
                                    <span class="text-sm font-bold">4.7/5</span>
                                </div>
                                <div class="w-full bg-gray-200 rounded-full h-2">
                                    <div class="bg-purple-600 h-2 rounded-full" style="width: 94%"></div>
                                </div>
                            </div>
                            <div>
                                <div class="flex justify-between items-center mb-2">
                                    <span class="text-sm font-medium">Rider Utilization</span>
                                    <span class="text-sm font-bold">78%</span>
                                </div>
                                <div class="w-full bg-gray-200 rounded-full h-2">
                                    <div class="bg-orange-600 h-2 rounded-full" style="width: 78%"></div>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- High-Demand Areas -->
                    <div class="bg-white rounded-xl shadow-lg p-6">
                        <h3 class="text-xl font-bold mb-6">High-Demand Areas</h3>
                        <div class="space-y-4">
                            <div class="flex items-center justify-between p-3 bg-red-50 rounded-lg">
                                <div>
                                    <p class="font-semibold">Shar-e-Naw</p>
                                    <p class="text-sm text-gray-600">Commercial District</p>
                                </div>
                                <div class="text-right">
                                    <p class="font-bold text-red-600">89 orders/day</p>
                                    <p class="text-sm text-gray-600">+15% vs last week</p>
                                </div>
                            </div>
                            <div class="flex items-center justify-between p-3 bg-orange-50 rounded-lg">
                                <div>
                                    <p class="font-semibold">Wazir Akbar Khan</p>
                                    <p class="text-sm text-gray-600">Business District</p>
                                </div>
                                <div class="text-right">
                                    <p class="font-bold text-orange-600">67 orders/day</p>
                                    <p class="text-sm text-gray-600">+8% vs last week</p>
                                </div>
                            </div>
                            <div class="flex items-center justify-between p-3 bg-yellow-50 rounded-lg">
                                <div>
                                    <p class="font-semibold">Karte-4</p>
                                    <p class="text-sm text-gray-600">Residential Area</p>
                                </div>
                                <div class="text-right">
                                    <p class="font-bold text-yellow-600">45 orders/day</p>
                                    <p class="text-sm text-gray-600">+3% vs last week</p>
                                </div>
                            </div>
                        </div>

                        <!-- Dynamic Pricing Suggestions -->
                        <div class="mt-6 p-4 bg-blue-50 rounded-lg">
                            <h4 class="font-semibold mb-3">Dynamic Pricing Suggestions</h4>
                            <div class="space-y-2 text-sm">
                                <div class="flex items-center justify-between">
                                    <span>Peak Hours (12-2 PM)</span>
                                    <span class="text-blue-600 font-semibold">+20% surge</span>
                                </div>
                                <div class="flex items-center justify-between">
                                    <span>Rainy Weather</span>
                                    <span class="text-blue-600 font-semibold">+15% surge</span>
                                </div>
                                <div class="flex items-center justify-between">
                                    <span>High-demand Areas</span>
                                    <span class="text-blue-600 font-semibold">+10% surge</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Revenue Optimization -->
                <div class="bg-white rounded-xl shadow-lg p-6 mt-6">
                    <h3 class="text-xl font-bold mb-6">Revenue Optimization</h3>
                    <div class="grid md:grid-cols-3 gap-6">
                        <div class="text-center p-4 border rounded-lg">
                            <div class="w-16 h-16 bg-green-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-store text-green-600 text-xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Store Partnerships</h4>
                            <p class="text-sm text-gray-600 mb-3">Identify high-potential stores for partnership</p>
                            <div class="text-2xl font-bold text-green-600 mb-2">23</div>
                            <p class="text-xs text-gray-500">Potential partners identified</p>
                        </div>
                        <div class="text-center p-4 border rounded-lg">
                            <div class="w-16 h-16 bg-blue-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-ad text-blue-600 text-xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Advertisement Revenue</h4>
                            <p class="text-sm text-gray-600 mb-3">Optimize ad placement and pricing</p>
                            <div class="text-2xl font-bold text-blue-600 mb-2">8,200</div>
                            <p class="text-xs text-gray-500">AFN monthly ad revenue</p>
                        </div>
                        <div class="text-center p-4 border rounded-lg">
                            <div class="w-16 h-16 bg-purple-100 rounded-full flex items-center justify-center mx-auto mb-4">
                                <i class="fas fa-crown text-purple-600 text-xl"></i>
                            </div>
                            <h4 class="font-semibold mb-2">Premium Subscriptions</h4>
                            <p class="text-sm text-gray-600 mb-3">Convert users to premium plans</p>
                            <div class="text-2xl font-bold text-purple-600 mb-2">156</div>
                            <p class="text-xs text-gray-500">Active premium subscribers</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Interface Management
        function showInterface(interfaceName) {
            // Hide all interfaces
            document.querySelectorAll('.interface').forEach(el => el.classList.add('hidden'));
            
            // Show selected interface
            document.getElementById(interfaceName + '-interface').classList.remove('hidden');
        }

        // Customer Section Management
        function showCustomerSection(sectionName) {
            // Hide all customer sections
            document.querySelectorAll('.customer-section').forEach(el => el.classList.add('hidden'));
            
            // Show selected section
            document.getElementById('customer-' + sectionName).classList.remove('hidden');
        }

        // Admin Section Management
        function showAdminSection(sectionName) {
            // Hide all admin sections
            document.querySelectorAll('.admin-section').forEach(el => el.classList.add('hidden'));
            
            // Show selected section
            document.getElementById('admin-' + sectionName).classList.remove('hidden');
        }

        // Service Selection
        function selectService(serviceType) {
            // Remove selection from all service cards
            document.querySelectorAll('[onclick*="selectService"]').forEach(el => {
                el.classList.remove('border-blue-400', 'bg-blue-50');
                el.classList.add('border-gray-200');
            });
            
            // Add selection to clicked card
            event.target.closest('[onclick*="selectService"]').classList.remove('border-gray-200');
            event.target.closest('[onclick*="selectService"]').classList.add('border-blue-400', 'bg-blue-50');
            
            // Show/hide package details
            const packageDetails = document.getElementById('package-details');
            if (serviceType === 'package') {
                packageDetails.classList.remove('hidden');
            } else {
                packageDetails.classList.add('hidden');
            }
        }

        // Order Placement
        function placeOrder() {
            // Simulate order placement
            alert('Order placed successfully! Searching for nearby riders...');
            
            // Switch to tracking section
            showCustomerSection('tracking');
            
            // Show success notification
            setTimeout(() => {
                alert('Rider found! Mohammad Ahmadi is on the way to pickup location.');
            }, 2000);
        }

        // Accept Order (Rider)
        function acceptOrder() {
            // Hide available orders and show active delivery
            document.querySelector('.bg-white.rounded-xl.shadow-lg.p-6.mb-8:has(h3:contains("Available Orders"))').style.display = 'none';
            document.getElementById('active-delivery').classList.remove('hidden');
            
            alert('Order accepted! Navigate to pickup location.');
        }

        // Toggle Online Status (Rider)
        function toggleOnlineStatus() {
            const toggle = event.target;
            const statusText = toggle.nextElementSibling;
            
            if (toggle.checked) {
                statusText.textContent = 'Online';
                statusText.classList.remove('text-gray-500');
                statusText.classList.add('text-green-600');
            } else {
                statusText.textContent = 'Offline';
                statusText.classList.remove('text-green-600');
                statusText.classList.add('text-gray-500');
            }
        }

        // Initialize with home interface
        document.addEventListener('DOMContentLoaded', function() {
            showInterface('home');
        });

        // Simulate real-time updates
        setInterval(() => {
            // Update earnings, order counts, etc.
            const earnings = document.querySelector('.text-2xl.font-bold.text-green-600');
            if (earnings && earnings.textContent.includes('AFN')) {
                const currentAmount = parseInt(earnings.textContent.replace(/[^\d]/g, ''));
                const newAmount = currentAmount + Math.floor(Math.random() * 50);
                earnings.textContent = newAmount.toLocaleString() + ' AFN';
            }
        }, 30000); // Update every 30 seconds

        // Add notification system
        function showNotification(message, type = 'info') {
            const notification = document.createElement('div');
            notification.className = `fixed top-24 right-4 p-4 rounded-lg<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'96b83d7b969c909b',t:'MTc1NDU4NTA4My4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script>
