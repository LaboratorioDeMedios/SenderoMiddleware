![Sendero](http://sendero.uy/images/logo-white.png)

Sendero Middleware
==================

This component (fully developed in Python3) is the man in the middle between [Sendero Server](https://github.com/LaboratorioDeMedios/SenderoServer) and Sendero Wireless controllers. It is responsible for the management of the wireless devices and the delivery of Sendero frame data to the them. It is also capable of generating its own color content.

To use Sendero Middleware with Sendero Server, it must be configured as a `Device` in Sendero Server's configuration file. 

It offers the following **execution modes**:

- `devserver`:    Starts a straming session with device management.
                  Allows an extra parameter to send a simulated streaming among `sin` | `flash` | `artnet`.


- `prodserver`:   Starts a streaming session with device management, control and keep-alive servers.
                  Allows an extra parameter to send a simulated streaming.

Stream modes (**extra params**):

- `sin`:          Streams a sin-controlled lighting pattern.

- `flash`:        Streams a flash pattern in broadcast mode.

- `artnet`:       Receives, adapts and redirects ArtNet packets.


                
Modules
-------

- `config`: Stores all the configurable settings.

- `streaming`: Module responsible of the translation and redirection of Art-Net packets.

- `utils`: A set of utilitary methods for the whole app.

- `devices`: Device manager, is responsible for all the actions related to a wireless device. 
(Registering, Controlling, etc...)

- `networking`: Used to manage multicast networking.
              For artworks containing a lot of pixels, the size of the packet can be divided using mutliple multicast groups. 

Settings
--------

All configurations are commented in the `config.py` module. 


Invocation
---------- 
```
python3 middleware.py < execution mode > [extra params]
```

-------------

For more information about Sendero Project go to the [base repository](https://github.com/LaboratorioDeMedios/Sendero).

