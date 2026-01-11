<img width="1535" height="691" alt="image" src="https://github.com/user-attachments/assets/03282f46-a32c-4539-97e3-56fa43a9b006" />

This diagram shows how a Smart TV in one house is able to watch movies from a Jellyfin server located in another house, even though both houses are on different networks.
The important part is that this is done securely, without exposing the server directly to the internet.

### Understanding the setup -

Think of this as two separate homes:

- **House Brown** → This is where the Smart TV is located

- **House Bayko** → This is where the Jellyfin media server is running

**Both houses have:**

- Their own local networks

- Their own routers

A small device called a white box, which acts like a special gateway

Between these two houses, we have a VPN tunnel.
This VPN makes both houses feel like they are part of the same private network, even though they are physically far apart.

### What the “white boxes” actually do

The white boxes are very important here.
You can think of them as trusted messengers between the two houses.

- They know how to send traffic to the other house

- They use the VPN tunnel to do it securely

- They make sure private IP addresses still work across locations

So instead of traffic going openly over the internet, it goes through a protected path.

### Now let’s walk through the traffic

**- Step 1: Smart TV makes a request**

Someone in House Brown opens the Jellyfin app on the Smart TV and selects a movie to watch.
At this moment, the TV simply knows one thing: “I need to contact the Jellyfin server.”
So it creates a network request using its own IP address and a random source port, and sets the destination IP of the Jellyfin server.

The TV doesn’t care where the server physically is—it just sends the request like it would for any other service.

**- Step 2: Request goes to the home router**

Since the Smart TV is part of the local home network, it always sends traffic to the home router first.
The router looks at the destination IP and checks its routing table.

At this point, the router understands:

This server is not inside the local network

The traffic needs to be forwarded somewhere else

So the router decides where to send the packet next.

**- Step 3: Router sends traffic to the white box**

The router knows that any traffic meant for the other house must go through the white box.
So instead of sending it to the internet normally, it forwards the packet to the white box.

You can think of the white box as a special exit door that knows how to reach the other house securely.

**- Step 4: Traffic goes through the VPN**

Once the white box receives the packet, it places it into the VPN tunnel.
This is where security comes in.

At this stage:

- The packet is encrypted

- Anyone on the internet can only see encrypted data

- The original IP addresses stay private

The packet now travels across the internet, but safely, as if it were inside a sealed pipe, until it reaches House Bayko.

**- Step 5: Other white box receives the traffic**

On the Bayko side, the second white box receives the encrypted packet.
It decrypts the traffic and checks the destination address.

**The white box understands:**

“This traffic is meant for my internal network.”

So it forwards the packet to the local router inside House Bayko.

**- Step 6: Traffic reaches the Jellyfin server**

The local router sends the packet to the Jellyfin server, which is running inside a Docker container and listening on port 8096.

The Jellyfin server receives the request, processes it, and starts sending the media data back.

From this point onward, the response travels back using the exact same path, just in reverse, until it reaches the Smart TV.





















### How the response comes back

Once the Jellyfin server sends the video data:

- The response follows the same path back

- Jellyfin → router → white box → VPN → other white box → router → Smart TV

Because the path is stable and secure, streaming works smoothly.




