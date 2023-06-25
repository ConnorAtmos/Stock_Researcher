[Back to README.md](/README.md)

# DOCUMENTATION TABLE OF CONTENTS #

This is the documentation for the project Stock_Researcher.

## INSTRUCTIONS.md ##

[0. HOW TO USE THIS TEMPLATE](/docs/INSTRUCTIONS.md#0-how-to-use-this-template)

[1. HOW TO INSTALL ANACONDA](/docs/INSTRUCTIONS.md#1-how-to-install-anaconda)

[2. HOW TO CREATE CONDA ENVIRONMENT](/docs/INSTRUCTIONS.md#2-how-to-create-conda-environment)

[3. HOW TO CONNECT INTERPRETER TO JETBRAINS GATEWAY](/docs/INSTRUCTIONS.md#3-how-to-connect-interpreter-to-jetbrains-gateway)

[4. HOW TO INSTALL REQUIREMENTS](/docs/INSTRUCTIONS.md#4-how-to-install-requirements)

[5. HOW TO INSTALL SERVICE](/docs/INSTRUCTIONS.md#5-how-to-install-service)

[A. HOW TO REMOVE CONDA ENVIRONMENT](/docs/INSTRUCTIONS.md#a-how-to-remove-conda-environment)

[B. HOW TO UNINSTALL SERVICE](/docs/INSTRUCTIONS.md#b-how-to-uninstall-service)

# API #


<details>
<summary>

## Documentation For [main.py](/docs/MAIN.md)

</summary>


 <details>
<summary>

### > [function main](/docs/MAIN.md#function-main) 



</summary>

[def main():](./../main.py#L13) 



</details>

<br></details>


<details>
<summary>

## Documentation For [toolbox/ticker_retreival.py](/docs/TOOLBOX-TICKER_RETREIVAL.md)

</summary>


 <details>
<summary>

### > [function set_storage_path](/docs/TOOLBOX-TICKER_RETREIVAL.md#function-set_storage_path) 



</summary>

[def set_storage_path(database_path: str, make_dir=False):](./../toolbox/ticker_retreival.py#L8) 

Note


```python
    This function is used to set the path to the database. The database is a
```

Return


```python
    None
```

Example


```python
    from toolbox import ticker_retreival
    ticker_retreival.set_storage_path('C:/Users/username/PycharmProjects/stock_analysis/database')
```



</details>


 <details>
<summary>

### > [function get_tickers](/docs/TOOLBOX-TICKER_RETREIVAL.md#function-get_tickers) 



</summary>

[def get_tickers(days_reset_frequency=7, request_fresh=False):](./../toolbox/ticker_retreival.py#L37) 

Note


```python
    This function is used to get the list of tickers. The tickers are saved in the database. If the tickers are older
```

Return


```python
    tickers: list
        List of tickers
```

Example


```python
    from toolbox import ticker_retreival
    ticker_retreival.set_storage_path('C:/Users/username/PycharmProjects/stock_analysis/database')
    tickers = ticker_retreival.get_tickers()
```

Reference


```python
    https://levelup.gitconnected.com/how-to-get-all-stock-symbols-a73925c16a1b
```



</details>


 <details>
<summary>

### > [function get_rejected_tickers](/docs/TOOLBOX-TICKER_RETREIVAL.md#function-get_rejected_tickers) 



</summary>

[def get_rejected_tickers(days_reset_frequency=7, request_fresh=False):](./../toolbox/ticker_retreival.py#L112) 

Note


```python
    This function is used to get the list of rejected tickers.
    W = When Issued, or can be arrested for fraud
    R = Rights Issue
    P = “First Preferred Issue”. Preferred stocks are a separate entity.
    Q = Bankruptcy
```

Return


```python
    rejected_tickers: list
        List of rejected tickers
```

Example


```python
    from toolbox import ticker_retreival
    ticker_retreival.set_storage_path('C:/Users/username/PycharmProjects/stock_analysis/database')
    rejected_tickers = ticker_retreival.get_rejected_tickers()
```

Reference


```python
    https://levelup.gitconnected.com/how-to-get-all-stock-symbols-a73925c16a1b
```



</details>


 <details>
<summary>

### > [function get_ticker_information](/docs/TOOLBOX-TICKER_RETREIVAL.md#function-get_ticker_information) 



</summary>

[def get_ticker_information(symbol: str, days_reset_frequency=14, request_fresh=False, cooldown_counter=0):](./../toolbox/ticker_retreival.py#L151) 

Note


```python
    This function is used to get the information for a given ticker. The information is saved in the database. If the
```

Return


```python
    stock_info: dict
        Dictionary of stock information
```

Example


```python
    from toolbox import ticker_retreival
    ticker_retreival.set_storage_path('C:/Users/username/PycharmProjects/stock_analysis/database')
    stock_info = ticker_retreival.get_ticker_information('MSFT')
    name = stock_info['shortName']
    website = stock_info['website']
    description = stock_info['longBusinessSummary']
```



</details>


 <details>
<summary>

### > [function get_all_ticker_information](/docs/TOOLBOX-TICKER_RETREIVAL.md#function-get_all_ticker_information) 



</summary>

[def get_all_ticker_information(days_reset_frequency=1, request_fresh=False):](./../toolbox/ticker_retreival.py#L232) 

Note


```python
    This function is used to get the information for all tickers. The information is saved in the database. If the
```

Return


```python
    all_info: dict
        Dictionary of stock information for all tickers
```

Example


```python
    from toolbox import ticker_retreival
    ticker_retreival.set_storage_path('C:/Users/username/PycharmProjects/stock_analysis/database')
    all_info = ticker_retreival.get_all_ticker_information()
    print(all_info['MSFT']['shortName'])
```



</details>

<br></details>


<details>
<summary>

## Documentation For [toolbox/queue_local.py](/docs/TOOLBOX-QUEUE_LOCAL.md)

</summary>


 <details>
<summary>

### > [class Queue](/docs/TOOLBOX-QUEUE_LOCAL.md#class-queue) 



</summary>

[class Queue:](./../toolbox/queue_local.py#L2) 

Note


```python
    A queue is a data structure that follows the First In First Out (FIFO) principle.
    This means that the first item added to the queue will be the first item removed from the queue.
    A queue can be implemented using a list or a linked list.
```

Example


```python
    queue = Queue([1, 2, 3, 4, 5], 10)

    a = queue.dequeue()
    print(a)
```

Reference


```python
    https://en.wikipedia.org/wiki/Queue_(abstract_data_type)
```




 <details>
<summary>

### >  > [function Queue.init](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueinit) 



</summary>

[def __init__(self, queue_list: list = None, max_size: int = None):](./../toolbox/queue_local.py#L30) 

Note


```python
        If the queue_list is not None, then the queue will be initialized with the list
        If the max_size is not None, then the queue will be initialized with the max_size
```

Return


```python
        None
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], 10)

        a = queue.dequeue()
        print(a)
```



</details>


 <details>
<summary>

### >  > [function Queue.enqueue](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueenqueue) 



</summary>

[def enqueue(self, item):](./../toolbox/queue_local.py#L61) 

Note


```python
        Adds the item to the end of the queue
```

Return


```python
        None
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)
        print(queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.dequeue](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuedequeue) 



</summary>

[def dequeue(self):](./../toolbox/queue_local.py#L90) 

Note


```python
        Removes the first item from the queue
```

Return


```python
        item: any
            The item that was removed from the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        a = queue.dequeue()
        print(a)
```



</details>


 <details>
<summary>

### >  > [function Queue.size](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuesize) 



</summary>

[def size(self) -> int:](./../toolbox/queue_local.py#L118) 

Note


```python
        Returns the size of the queue
```

Return


```python
        size: int
            The size of the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        print(queue.size())
```



</details>


 <details>
<summary>

### >  > [function Queue.is_empty](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueis_empty) 



</summary>

[def is_empty(self) -> bool:](./../toolbox/queue_local.py#L146) 

Note


```python
        Returns True if the queue is empty, False otherwise
```

Return


```python
        is_empty: bool
            True if the queue is empty, False otherwise
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)

        print(queue.is_empty())
```



</details>


 <details>
<summary>

### >  > [function Queue.peek](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuepeek) 



</summary>

[def peek(self):](./../toolbox/queue_local.py#L173) 

Note


```python
        Returns the first item in the queue without removing it
```

Return


```python
        item: any
            The first item in the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        a = queue.peek()
        print(a)
```



</details>


 <details>
<summary>

### >  > [function Queue.get_list](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueget_list) 



</summary>

[def get_list(self):](./../toolbox/queue_local.py#L201) 

Note


```python
        Returns the list of items in the queue
```

Return


```python
        list: list
            The list of items in the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        a = queue.get_list()
        print(a)
```



</details>


 <details>
<summary>

### >  > [function Queue.len](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuelen) 



</summary>

[def __len__(self):](./../toolbox/queue_local.py#L230) 

Note


```python
        Returns the size of the queue
```

Return


```python
        size: int
            The size of the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)

        print(len(queue))
```



</details>


 <details>
<summary>

### >  > [function Queue.copy](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuecopy) 



</summary>

[def copy(self):](./../toolbox/queue_local.py#L256) 

Note


```python
        Returns a copy of the queue
```

Return


```python
        new_queue: Queue
            A copy of the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        new_queue = queue.copy()
        print(new_queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.copy](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuecopy) 



</summary>

[def __copy__(self):](./../toolbox/queue_local.py#L288) 

Note


```python
        Returns a copy of the queue
```

Return


```python
        new_queue: Queue
            A copy of the queue
```

Example


```python
        queue = Queue(max_size=10)

        queue.enqueue(1)
        queue.enqueue(2)
        queue.enqueue(3)

        new_queue = queue.copy()
        print(new_queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.eq](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueeq) 



</summary>

[def __eq__(self, other):](./../toolbox/queue_local.py#L317) 

Note


```python
        Returns True if the queues are equal, False otherwise
```

Return


```python
        is_equal: bool
            True if the queues are equal, False otherwise
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)
        other = Queue([1, 2, 3, 4, 5], max_size=10)

        print(queue == other)
```



</details>


 <details>
<summary>

### >  > [function Queue.ne](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuene) 



</summary>

[def __ne__(self, other):](./../toolbox/queue_local.py#L348) 

Note


```python
        Returns True if the queues are not equal, False otherwise
```

Return


```python
        is_not_equal: bool
            True if the queues are not equal, False otherwise
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)
        other = Queue([1, 2, 3, 4, 5], max_size=10)

        print(queue != other)
```



</details>


 <details>
<summary>

### >  > [function Queue.getitem](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuegetitem) 



</summary>

[def __getitem__(self, index):](./../toolbox/queue_local.py#L373) 

Note


```python
        Returns the item at the given index
```

Return


```python
        item: any
            The item at the given index
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        print(queue[2])
```



</details>


 <details>
<summary>

### >  > [function Queue.setitem](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuesetitem) 



</summary>

[def __setitem__(self, index, value):](./../toolbox/queue_local.py#L397) 

Note


```python
        Sets the item at the given index to the given value
```

Return


```python
        None
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        queue[2] = 10
        print(queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.delitem](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuedelitem) 



</summary>

[def __delitem__(self, index):](./../toolbox/queue_local.py#L423) 

Note


```python
        Deletes the item at the given index
```

Return


```python
        None
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        del queue[2]
        print(queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.iter](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueiter) 



</summary>

[def __iter__(self):](./../toolbox/queue_local.py#L447) 

Note


```python
        Returns an iterator for the queue
```

Return


```python
        iter: iter
            An iterator for the queue
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        for item in queue:
            print(item)
```



</details>


 <details>
<summary>

### >  > [function Queue.reversed](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuereversed) 



</summary>

[def __reversed__(self):](./../toolbox/queue_local.py#L471) 

Note


```python
        Returns an iterator for the queue in reverse order
```

Return


```python
        reversed: iter
            An iterator for the queue in reverse order
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        for item in reversed(queue):
            print(item)
```



</details>


 <details>
<summary>

### >  > [function Queue.contains](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuecontains) 



</summary>

[def __contains__(self, item):](./../toolbox/queue_local.py#L495) 

Note


```python
        Returns True if the item is in the queue, False otherwise
```

Return


```python
        is_in: bool
            True if the item is in the queue, False otherwise
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        print(1 in queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.add](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueadd) 



</summary>

[def __add__(self, other):](./../toolbox/queue_local.py#L519) 

Note


```python
        Returns a new queue with the items from both queues
```

Return


```python
        new_queue: Queue
            A new queue with the items from both queues
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)
        other = Queue([6, 7, 8, 9, 10], max_size=10)

        new_queue = queue + other
        print(new_queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.iadd](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueiadd) 



</summary>

[def __iadd__(self, other):](./../toolbox/queue_local.py#L550) 

Note


```python
        Returns this queue with the items from both queues
```

Return


```python
        self: Queue
            This queue with the items from both queues
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)
        other = Queue([6, 7, 8, 9, 10], max_size=10)

        queue += other
        print(queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.mul](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuemul) 



</summary>

[def __mul__(self, other):](./../toolbox/queue_local.py#L578) 

Note


```python
        Returns a new queue with the items from this queue repeated the given number of times
```

Return


```python
        new_queue: Queue
            A new queue with the items from this queue repeated the given number of times
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        new_queue = queue * 3
        print(new_queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.imul](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queueimul) 



</summary>

[def __imul__(self, other):](./../toolbox/queue_local.py#L607) 

Note


```python
        Returns this queue with the items from this queue repeated the given number of times
```

Return


```python
        self: Queue
            This queue with the items from this queue repeated the given number of times
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        queue *= 3
        print(queue)
```



</details>


 <details>
<summary>

### >  > [function Queue.str](/docs/TOOLBOX-QUEUE_LOCAL.md#function-queuestr) 



</summary>

[def __str__(self):](./../toolbox/queue_local.py#L636) 

Note


```python
        Returns a string representation of the queue
```

Return


```python
        string: str
            A string representation of the queue
```

Example


```python
        queue = Queue([1, 2, 3, 4, 5], max_size=10)

        print(queue)
```



</details>

</details>

<br></details>


<details>
<summary>

## Documentation For [toolbox/database.py](/docs/TOOLBOX-DATABASE.md)

</summary>


 <details>
<summary>

### > [function set_storage_path](/docs/TOOLBOX-DATABASE.md#function-set_storage_path) 



</summary>

[def set_storage_path(path):](./../toolbox/database.py#L9) 

Note


```python
    This function is used to set the path to the folder where the database files will be stored
```

Parameter


```python
    path : str
        The path to the folder where the database files will be stored
```

Return


```python
    None
        This function does not return anything
```

Example


```python
    set_storage_path('C:/Users/JohnDoe/Documents/MyDatabase')
```

Reference


```python
    No Links
```



</details>


 <details>
<summary>

### > [function slugify](/docs/TOOLBOX-DATABASE.md#function-slugify) 



</summary>

[def slugify(value, allow_unicode=False):](./../toolbox/database.py#L41) 

Note


```python
    This function is used to slugify strings, which basically means to remove all special characters and replace them with dashes.
    This is useful for creating file names from strings.
```

Parameter


```python
    value : str
        The string to be slugified
    allow_unicode : bool
        Whether or not to allow unicode characters
```

Return


```python
    str
        The slugified string
```

Example


```python
    a = slugify('Hello World')
```

Reference


```python
    https://github.com/django/django/blob/master/django/utils/text.py
```



</details>


 <details>
<summary>

### > [function get](/docs/TOOLBOX-DATABASE.md#function-get) 



</summary>

[def get(name: str):](./../toolbox/database.py#L77) 

Note


```python
    This function is used to load objects from the database folder
```

Parameter


```python
    name : str
        The name of the file to be loaded
```

Return


```python
    object or None
        The object loaded from the file, could be anything
```

Example


```python
    spreadsheet_data = get('spreadsheet_people')
```

Reference


```python
    No Links
```



</details>


 <details>
<summary>

### > [function get_modified_date](/docs/TOOLBOX-DATABASE.md#function-get_modified_date) 



</summary>

[def get_modified_date(name: str):](./../toolbox/database.py#L112) 

Note


```python
    This function is used to get the last modified date of a file in the database folder
```

Parameter


```python
    name : str
        The name of the file to be loaded
```

Return


```python
    datetime.datetime or None
        The datetime object of the last modified date
```

Example


```python
    date = get_modified_date('spreadsheet_people')
```

Reference


```python
    No Links
```



</details>


 <details>
<summary>

### > [function save](/docs/TOOLBOX-DATABASE.md#function-save) 



</summary>

[def save(name: str, data: any) -> None:](./../toolbox/database.py#L147) 

Note


```python
    This function is used to save objects to the database folder
```

Parameter


```python
    name : str
        The name of the file to be saved
    data : any
        The data to be saved
```

Return


```python
    None
        This function does not return anything
```

Example


```python
    spreadsheet_data = {"People": ["Bill", "Kent", "Steve"], "Ages": [20, 30, 40]}

    save('spreadsheet_people', spreadsheet_data)
```

Reference


```python
    No Links
```



</details>


 <details>
<summary>

### > [function delete_database](/docs/TOOLBOX-DATABASE.md#function-delete_database) 



</summary>

[def delete_database(name: str) -> object:](./../toolbox/database.py#L182) 

Note


```python
    This function is used to delete objects from the database folder
```

Parameter


```python
    name : str
        The name of the file to be deleted
```

Return


```python
    object or None
        The object loaded from the file, could be anything
```

Example


```python
    spreadsheet_data = {"People": ["Bill", "Kent", "Steve"], "Ages": [20, 30, 40]}

    save('spreadsheet_people', spreadsheet_data)

    delete_database('spreadsheet_people')
```

Reference


```python
    No Links
```



</details>


 <details>
<summary>

### > [function save_key](/docs/TOOLBOX-DATABASE.md#function-save_key) 



</summary>

[def save_key(platform: str, key: str, override: bool = False) -> None:](./../toolbox/database.py#L220) 

Note


```python
    This function is used to save keys in a secure location
```

Parameter


```python
    platform: str
        The name of the platform to be saved (e.g. 'google')
    key: str
        The key to be saved (e.g. '<google_api_key>')
    override: bool
        Whether or not to override the key if it already exists
```

Return


```python
    None
        This function does not return anything
```

Example


```python
    save_key('google', '<google_api_key>')
```

Reference


```python
    https://www.nylas.com/blog/making-use-of-environment-variables-in-python/
```



</details>


 <details>
<summary>

### > [function load_key](/docs/TOOLBOX-DATABASE.md#function-load_key) 



</summary>

[def load_key(platform: str) -> str:](./../toolbox/database.py#L267) 

Note


```python
        This function is used to load keys from a secure location
```

Parameter


```python
        platform: str
            The key to be loaded (e.g. '<google_api_key>')
```

Return


```python
        str or None
            This function returns the key if it exists, otherwise it returns None
```

Example


```python
        key = load_key('google')
```

Reference


```python
        https://www.nylas.com/blog/making-use-of-environment-variables-in-python/
```



</details>

<br></details>

