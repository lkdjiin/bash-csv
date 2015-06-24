# Bash-csv

Some command line tools written in Bash to deal with CSV files.

## Dependencies

No dependencies, other than a decent version of Bash.

## Install

Put all `csvcolmerge` and `csvnames` somewhere in a folder under your path.

## csvnames

Display the name of each column from a CSV file.

    $ csvnames data/data.csv 
      1 year
      2 month
      3 day
      4 quantity

Type `csvnames -h` for help.

## csvcolmerge

Merge two or more columns into a new column in a CSV file.

    $ 1 csvcolmerge < data/data.csv -f 1,2,3 -t date -m-
    year,month,day,quantity,date
    1999,02,02,34,1999-02-02
    1999,06,12,42,1999-06-12
    2000,08,11,98,2000-08-11
    2001,01,27,21,2001-01-27

The effect is simpler to visualize using [csvlook](http://csvkit.readthedocs.org/en/0.9.1/index.html):

    $ csvcolmerge < data/data.csv -f 1,2,3 -t date -m- | csvlook
    |-------+-------+-----+----------+-------------|
    |  year | month | day | quantity | date        |
    |-------+-------+-----+----------+-------------|
    |  1999 | 02    | 02  | 34       | 1999-02-02  |
    |  1999 | 06    | 12  | 42       | 1999-06-12  |
    |  2000 | 08    | 11  | 98       | 2000-08-11  |
    |  2001 | 01    | 27  | 21       | 2001-01-27  |
    |-------+-------+-----+----------+-------------|

Type `csvcolmerge -h` for help.

## License

[GPLv3](http://www.gnu.org/licenses/gpl.html)

## Questions and/or Comments

Feel free to email [Xavier Nayrac](mailto:xavier.nayrac@gmail.com)
with any questions, or contact me on [twitter](https://twitter.com/lkdjiin).
