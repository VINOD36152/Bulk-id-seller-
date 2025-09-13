# Bulk-id-seller-
Digital online sell 
import React, { useEffect, useState } from "react";
const SAMPLE_PRODUCTS = [

function uid(prefix = "id") {

<div className="flex justify-between">

<div>

<div className="font-semibold">{p.title}</div>

<div className="text-sm text-gray-600">{p.type} — ${p.price}</div>

</div>

<div>

<button onClick={() => addToCart(p)} className="px-3 py-1 rounded bg-green-600 text-white">Add</button>

</div>

</div>

<div className="mt-3 text-sm text-gray-700">{p.description}</div>

{p.type === "digital" && p.downloadUrl && (

<div className="mt-2 text-xs text-gray-500">Demo download URL present</div>

)}

</div>

))}

</div>

</section>


<aside className="p-4 border rounded bg-gray-50">

<h3 className="font-semibold">Cart ({cart.length})</h3>

<div className="space-y-2 mt-2">

{cart.length === 0 && <div className="text-sm text-gray-500">Your cart is empty</div>}

{cart.map((c, idx) => (

<div key={idx} className="flex justify-between items-center p-2 border rounded">

<div className="text-sm">{c.title}</div>

<div className="flex items-center space-x-2">

<div className="text-sm">${c.price}</div>

<button onClick={() => removeFromCart(idx)} className="text-red-600 text-sm">Remove</button>

</div>

</div>

))}

</div>

<div className="vinod">

<div className="text-sm">Total: ${cart.reduce((s, it) => s + Number(it.price || 0), 0).toFixed(2)}</div>

<div className="mt-2">

<button onClick={() => placeOrder({ name: "Guest User", email: "vb757450@gmail.com" })} disabled={checkoutLoading} className="w-full px-3 py-2 rounded bg-indigo-600 text-white mt-2">{checkoutLoading ? 'Processing...' : 'Checkout (Demo)'}</button>

</div>

</div>


<div className="mt-4 text-xs text-gray-500">

This demo does not process real payments. Integrate Stripe/PayPal on your server for production.

</div>

</aside>

</div>

)}


{view === "admin" && <AdminPanel />}


{view === "orders" && <OrdersView />}

</main>


<footer className="mt-6 text-xs text-gray-500">

Demo storefront • Replace local storage & client-side key generation with a secure backend before going live.

</footer>

</div>

</div>

);

}
