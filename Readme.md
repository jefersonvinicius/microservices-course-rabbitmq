# RabbitMq

## Components

- Publisher (publish message)
- Exchange (proccess message and determines queue destiny)
- Queue
- Consumer (receive message)

Publisher -> Exchange -> Queue -> Consumer

## Exchange types
- Direct (send by specifics queues binded and with key informed)
- Fanout (send by all queues binded)
- Topic (send by queue with key informed, accept regex)

## Queues
- FIFO (first in, first out)
- Properties
    - Durable: should save message after shut down broker
    - Auto-delete: removed when consumer disconnect
    - Expiry: set max waiting time by messages ou consumers
    - Message TTL: message have Time To Live, in other words, have limite time to stay on queue
    - Overflow
        - Drop head: delete last message
        - Reject publish
    - Exclusive: only creator channel can access
    - Max length or bytes: max amount messages. When queue overflow, is applyed the rule defined in Overflow property

## Dead Letters Queues
- Message did not consumed by any consumer are send to the Dead Letters Queue, after they can be investigated by unproccess reasons 

## Lazy Queues
- Messages are stored when consumers not able handle many message in queue
- Require hight I/O
