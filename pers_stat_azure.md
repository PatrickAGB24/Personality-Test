{
    "metadata": {
        "kernelspec": {
            "name": "SQL",
            "display_name": "SQL",
            "language": "sql"
        },
        "language_info": {
            "name": "sql",
            "version": ""
        }
    },
    "nbformat_minor": 2,
    "nbformat": 4,
    "cells": [
        {
            "cell_type": "code",
            "source": [
                "DROP TABLE IF EXISTS personalitystats;\r\n",
                "CREATE TABLE personalitystats(\r\n",
                "    PersonalityType VARCHAR(4),\r\n",
                "    16PersStat FLOAT,\r\n",
                "    pMaxStat FLOAT\r\n",
                ")"
            ],
            "metadata": {
                "azdata_cell_guid": "8cb38548-c77c-42f3-af91-c938c18816e4",
                "language": "sql"
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Commands completed successfully"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Commands completed successfully"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:00.065"
                    },
                    "metadata": {}
                }
            ],
            "execution_count": 2
        },
        {
            "cell_type": "code",
            "source": [
                "SELECT * FROM personalitystats"
            ],
            "metadata": {
                "language": "sql",
                "azdata_cell_guid": "60429878-4595-4a12-b1fa-463e7bc6c560"
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "(12 row(s) affected)"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:01.019"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "execute_result",
                    "metadata": {},
                    "execution_count": 4,
                    "data": {
                        "application/vnd.dataresource+json": {
                            "schema": {
                                "fields": [
                                    {
                                        "name": "PersonalityType"
                                    },
                                    {
                                        "name": "16PersStat"
                                    },
                                    {
                                        "name": "pMaxStat"
                                    }
                                ]
                            },
                            "data": [
                                {
                                    "PersonalityType": "ESTJ",
                                    "16PersStat": "0.087",
                                    "pMaxStat": "0.045"
                                },
                                {
                                    "PersonalityType": "ESFJ",
                                    "16PersStat": "0.12",
                                    "pMaxStat": "0.023"
                                },
                                {
                                    "PersonalityType": "ISTJ",
                                    "16PersStat": "0.116",
                                    "pMaxStat": "0.086"
                                },
                                {
                                    "PersonalityType": "ISFJ",
                                    "16PersStat": "0.138",
                                    "pMaxStat": "0.028"
                                },
                                {
                                    "PersonalityType": "ESTP",
                                    "16PersStat": "0.043",
                                    "pMaxStat": "0.032"
                                },
                                {
                                    "PersonalityType": "ESFP",
                                    "16PersStat": "0.085",
                                    "pMaxStat": "0.029"
                                },
                                {
                                    "PersonalityType": "ISTP",
                                    "16PersStat": "0.054",
                                    "pMaxStat": "0.051"
                                },
                                {
                                    "PersonalityType": "ISFP",
                                    "16PersStat": "0.088",
                                    "pMaxStat": "0.028"
                                },
                                {
                                    "PersonalityType": "ENTJ",
                                    "16PersStat": "0.018",
                                    "pMaxStat": "0.04"
                                },
                                {
                                    "PersonalityType": "ENTP",
                                    "16PersStat": "0.032",
                                    "pMaxStat": "0.066"
                                },
                                {
                                    "PersonalityType": "INTJ",
                                    "16PersStat": "0.021",
                                    "pMaxStat": "0.078"
                                },
                                {
                                    "PersonalityType": "INTP",
                                    "16PersStat": "0.033",
                                    "pMaxStat": "0.119"
                                }
                            ]
                        },
                        "text/html": [
                            "<table>",
                            "<tr><th>PersonalityType</th><th>16PersStat</th><th>pMaxStat</th></tr>",
                            "<tr><td>ESTJ</td><td>0.087</td><td>0.045</td></tr>",
                            "<tr><td>ESFJ</td><td>0.12</td><td>0.023</td></tr>",
                            "<tr><td>ISTJ</td><td>0.116</td><td>0.086</td></tr>",
                            "<tr><td>ISFJ</td><td>0.138</td><td>0.028</td></tr>",
                            "<tr><td>ESTP</td><td>0.043</td><td>0.032</td></tr>",
                            "<tr><td>ESFP</td><td>0.085</td><td>0.029</td></tr>",
                            "<tr><td>ISTP</td><td>0.054</td><td>0.051</td></tr>",
                            "<tr><td>ISFP</td><td>0.088</td><td>0.028</td></tr>",
                            "<tr><td>ENTJ</td><td>0.018</td><td>0.04</td></tr>",
                            "<tr><td>ENTP</td><td>0.032</td><td>0.066</td></tr>",
                            "<tr><td>INTJ</td><td>0.021</td><td>0.078</td></tr>",
                            "<tr><td>INTP</td><td>0.033</td><td>0.119</td></tr>",
                            "</table>"
                        ]
                    }
                }
            ],
            "execution_count": 4
        },
        {
            "cell_type": "markdown",
            "source": [
                "It will be best to separate each of the personality types into the 4 dimensions used for each"
            ],
            "metadata": {
                "azdata_cell_guid": "fc61dc9c-bca6-4126-a1a8-2d67ae63fad2"
            },
            "attachments": {}
        },
        {
            "cell_type": "code",
            "source": [
                "ALTER TABLE personalitystats\r\n",
                "ADD COLUMN (\r\n",
                "Dim1 VARCHAR(1),\r\n",
                "Dim2 VARCHAR(1),\r\n",
                "Dim3 VARCHAR(1),\r\n",
                "Dim4 VARCHAR(1)\r\n",
                ");\r\n",
                "UPDATE personalitystats\r\n",
                "SET Dim1 = SUBSTRING(Personalitytype,1,1), Dim2= SUBSTRING(Personalitytype,2,1), \r\n",
                "Dim3= SUBSTRING(Personalitytype,3,1),Dim4= SUBSTRING(Personalitytype,4,1);"
            ],
            "metadata": {
                "azdata_cell_guid": "435aa410-154d-47cf-8a0a-293cf624f753",
                "language": "sql",
                "tags": []
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Commands completed successfully"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Commands completed successfully"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:00.021"
                    },
                    "metadata": {}
                }
            ],
            "execution_count": 5
        },
        {
            "cell_type": "code",
            "source": [
                "SELECT * FROM personalitystats"
            ],
            "metadata": {
                "language": "sql",
                "azdata_cell_guid": "066c52d0-24f6-4129-8488-7a32938a1d4a"
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "(12 row(s) affected)"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:01.009"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "execute_result",
                    "metadata": {},
                    "execution_count": 6,
                    "data": {
                        "application/vnd.dataresource+json": {
                            "schema": {
                                "fields": [
                                    {
                                        "name": "PersonalityType"
                                    },
                                    {
                                        "name": "16PersStat"
                                    },
                                    {
                                        "name": "pMaxStat"
                                    },
                                    {
                                        "name": "Dim1"
                                    },
                                    {
                                        "name": "Dim2"
                                    },
                                    {
                                        "name": "Dim3"
                                    },
                                    {
                                        "name": "Dim4"
                                    }
                                ]
                            },
                            "data": [
                                {
                                    "PersonalityType": "ESTJ",
                                    "16PersStat": "0.087",
                                    "pMaxStat": "0.045",
                                    "Dim1": "E",
                                    "Dim2": "S",
                                    "Dim3": "T",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "ESFJ",
                                    "16PersStat": "0.12",
                                    "pMaxStat": "0.023",
                                    "Dim1": "E",
                                    "Dim2": "S",
                                    "Dim3": "F",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "ISTJ",
                                    "16PersStat": "0.116",
                                    "pMaxStat": "0.086",
                                    "Dim1": "I",
                                    "Dim2": "S",
                                    "Dim3": "T",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "ISFJ",
                                    "16PersStat": "0.138",
                                    "pMaxStat": "0.028",
                                    "Dim1": "I",
                                    "Dim2": "S",
                                    "Dim3": "F",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "ESTP",
                                    "16PersStat": "0.043",
                                    "pMaxStat": "0.032",
                                    "Dim1": "E",
                                    "Dim2": "S",
                                    "Dim3": "T",
                                    "Dim4": "P"
                                },
                                {
                                    "PersonalityType": "ESFP",
                                    "16PersStat": "0.085",
                                    "pMaxStat": "0.029",
                                    "Dim1": "E",
                                    "Dim2": "S",
                                    "Dim3": "F",
                                    "Dim4": "P"
                                },
                                {
                                    "PersonalityType": "ISTP",
                                    "16PersStat": "0.054",
                                    "pMaxStat": "0.051",
                                    "Dim1": "I",
                                    "Dim2": "S",
                                    "Dim3": "T",
                                    "Dim4": "P"
                                },
                                {
                                    "PersonalityType": "ISFP",
                                    "16PersStat": "0.088",
                                    "pMaxStat": "0.028",
                                    "Dim1": "I",
                                    "Dim2": "S",
                                    "Dim3": "F",
                                    "Dim4": "P"
                                },
                                {
                                    "PersonalityType": "ENTJ",
                                    "16PersStat": "0.018",
                                    "pMaxStat": "0.04",
                                    "Dim1": "E",
                                    "Dim2": "N",
                                    "Dim3": "T",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "ENTP",
                                    "16PersStat": "0.032",
                                    "pMaxStat": "0.066",
                                    "Dim1": "E",
                                    "Dim2": "N",
                                    "Dim3": "T",
                                    "Dim4": "P"
                                },
                                {
                                    "PersonalityType": "INTJ",
                                    "16PersStat": "0.021",
                                    "pMaxStat": "0.078",
                                    "Dim1": "I",
                                    "Dim2": "N",
                                    "Dim3": "T",
                                    "Dim4": "J"
                                },
                                {
                                    "PersonalityType": "INTP",
                                    "16PersStat": "0.033",
                                    "pMaxStat": "0.119",
                                    "Dim1": "I",
                                    "Dim2": "N",
                                    "Dim3": "T",
                                    "Dim4": "P"
                                }
                            ]
                        },
                        "text/html": [
                            "<table>",
                            "<tr><th>PersonalityType</th><th>16PersStat</th><th>pMaxStat</th><th>Dim1</th><th>Dim2</th><th>Dim3</th><th>Dim4</th></tr>",
                            "<tr><td>ESTJ</td><td>0.087</td><td>0.045</td><td>E</td><td>S</td><td>T</td><td>J</td></tr>",
                            "<tr><td>ESFJ</td><td>0.12</td><td>0.023</td><td>E</td><td>S</td><td>F</td><td>J</td></tr>",
                            "<tr><td>ISTJ</td><td>0.116</td><td>0.086</td><td>I</td><td>S</td><td>T</td><td>J</td></tr>",
                            "<tr><td>ISFJ</td><td>0.138</td><td>0.028</td><td>I</td><td>S</td><td>F</td><td>J</td></tr>",
                            "<tr><td>ESTP</td><td>0.043</td><td>0.032</td><td>E</td><td>S</td><td>T</td><td>P</td></tr>",
                            "<tr><td>ESFP</td><td>0.085</td><td>0.029</td><td>E</td><td>S</td><td>F</td><td>P</td></tr>",
                            "<tr><td>ISTP</td><td>0.054</td><td>0.051</td><td>I</td><td>S</td><td>T</td><td>P</td></tr>",
                            "<tr><td>ISFP</td><td>0.088</td><td>0.028</td><td>I</td><td>S</td><td>F</td><td>P</td></tr>",
                            "<tr><td>ENTJ</td><td>0.018</td><td>0.04</td><td>E</td><td>N</td><td>T</td><td>J</td></tr>",
                            "<tr><td>ENTP</td><td>0.032</td><td>0.066</td><td>E</td><td>N</td><td>T</td><td>P</td></tr>",
                            "<tr><td>INTJ</td><td>0.021</td><td>0.078</td><td>I</td><td>N</td><td>T</td><td>J</td></tr>",
                            "<tr><td>INTP</td><td>0.033</td><td>0.119</td><td>I</td><td>N</td><td>T</td><td>P</td></tr>",
                            "</table>"
                        ]
                    }
                }
            ],
            "execution_count": 6
        },
        {
            "cell_type": "markdown",
            "source": [
                "Now we will check what the total percentage for both statistics"
            ],
            "metadata": {
                "azdata_cell_guid": "5ed8cd66-1c0d-4f0a-a42b-f19abfec38a4"
            },
            "attachments": {}
        },
        {
            "cell_type": "code",
            "source": [
                "SELECT SUM(16PersStat), SUM(pMaxStat) FROM personalitystats"
            ],
            "metadata": {
                "azdata_cell_guid": "08515f08-524f-48b7-845c-68bdab6476db",
                "language": "sql"
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "(1 row(s) affected)"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:01.016"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "execute_result",
                    "metadata": {},
                    "execution_count": 7,
                    "data": {
                        "application/vnd.dataresource+json": {
                            "schema": {
                                "fields": [
                                    {
                                        "name": "SUM(16PersStat)"
                                    },
                                    {
                                        "name": "SUM(pMaxStat)"
                                    }
                                ]
                            },
                            "data": [
                                {
                                    "SUM(16PersStat)": "0.8349999915808439",
                                    "SUM(pMaxStat)": "0.6250000093132257"
                                }
                            ]
                        },
                        "text/html": [
                            "<table>",
                            "<tr><th>SUM(16PersStat)</th><th>SUM(pMaxStat)</th></tr>",
                            "<tr><td>0.8349999915808439</td><td>0.6250000093132257</td></tr>",
                            "</table>"
                        ]
                    }
                }
            ],
            "execution_count": 7
        },
        {
            "cell_type": "markdown",
            "source": [
                "The sums of the known personality stats are given and are not equal to one because of the unknown pMax Statistics for some personality types. We will now check the ranking of each personality type trait:\n",
                "\n",
                "- E for Extraversion\n",
                "- I for Introversion\n",
                "- S for Sensing\n",
                "- N for iNtuition\n",
                "- T for Thinking\n",
                "- F for Feeling\n",
                "- J for Judging\n",
                "- P for Perceiving"
            ],
            "metadata": {
                "language": "",
                "azdata_cell_guid": "0b753155-9edb-48db-a812-170fe16126a4"
            },
            "attachments": {}
        },
        {
            "cell_type": "code",
            "source": [
                "SELECT Dim1 AS Dimension, 16PersStat, pMaxStat, \r\n",
                "RANK() OVER(ORDER BY 16PersStat DESC) AS RANK_BY_16Pers,  \r\n",
                "RANK() OVER(ORDER BY pMaxStat DESC) AS RANK_BY_pMax,\r\n",
                "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1) FROM\r\n",
                "((WITH temporarytable(Dim1,perssum,pMaxsum) AS (SELECT Dim1, SUM(16PersStat),SUM(pMaxStat) FROM personalitystats\r\n",
                "GROUP BY Dim1),\r\n",
                "counttable(perstotal,pMaxtotal) AS (SELECT SUM(16PersStat),SUM(pMaxStat) FROM personalitystats)\r\n",
                "SELECT Dim1, ROUND(perssum/perstotal,5) AS 16PersStat,ROUND(pMaxsum/pMaxtotal,5) AS pMaxStat FROM temporarytable,counttable)\r\n",
                "UNION\r\n",
                "(WITH temporarytable(Dim2,perssum,pMaxsum) AS (SELECT Dim2, SUM(16PersStat),SUM(pMaxStat) FROM personalitystats\r\n",
                "GROUP BY Dim2),\r\n",
                "counttable(perstotal,pMaxtotal) AS (SELECT SUM(16PersStat),SUM(pMaxStat) FROM personalitystats)\r\n",
                "SELECT Dim2, ROUND(perssum/perstotal,5) AS 16PersStat,ROUND(pMaxsum/pMaxtotal,5) AS pMaxStat FROM temporarytable,counttable)\r\n",
                "UNION\r\n",
                "(WITH temporarytable(Dim3,perssum,pMaxsum) AS (SELECT Dim3, SUM(16PersStat),SUM(pMaxStat) FROM personalitystats\r\n",
                "GROUP BY Dim3),\r\n",
                "counttable(perstotal,pMaxtotal) AS (SELECT SUM(16PersStat),SUM(pMaxStat) FROM personalitystats)\r\n",
                "SELECT Dim3, ROUND(perssum/perstotal,5) AS 16PersStat,ROUND(pMaxsum/pMaxtotal,5) AS pMaxStat FROM temporarytable,counttable)\r\n",
                "UNION\r\n",
                "(WITH temporarytable(Dim4,perssum,pMaxsum) AS (SELECT Dim4, SUM(16PersStat),SUM(pMaxStat) FROM personalitystats\r\n",
                "GROUP BY Dim4),\r\n",
                "counttable(perstotal,pMaxtotal) AS (SELECT SUM(16PersStat),SUM(pMaxStat) FROM personalitystats)\r\n",
                "SELECT Dim4, ROUND(perssum/perstotal,5) AS 16PersStat,ROUND(pMaxsum/pMaxtotal,5) AS pMaxStat FROM temporarytable,counttable)) AS main_table;"
            ],
            "metadata": {
                "azdata_cell_guid": "1959ee22-844b-4431-a785-546c22461b82",
                "language": "sql"
            },
            "outputs": [
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "(8 row(s) affected)"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "display_data",
                    "data": {
                        "text/html": "Total execution time: 00:00:01.006"
                    },
                    "metadata": {}
                },
                {
                    "output_type": "execute_result",
                    "execution_count": 42,
                    "data": {
                        "application/vnd.dataresource+json": {
                            "schema": {
                                "fields": [
                                    {
                                        "name": "Dimension"
                                    },
                                    {
                                        "name": "16PersStat"
                                    },
                                    {
                                        "name": "pMaxStat"
                                    },
                                    {
                                        "name": "RANK_BY_16Pers"
                                    },
                                    {
                                        "name": "RANK_BY_pMax"
                                    },
                                    {
                                        "name": "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)"
                                    }
                                ]
                            },
                            "data": [
                                {
                                    "Dimension": "T",
                                    "16PersStat": "0.48383",
                                    "pMaxStat": "0.8272",
                                    "RANK_BY_16Pers": "5",
                                    "RANK_BY_pMax": "1",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "3.0"
                                },
                                {
                                    "Dimension": "I",
                                    "16PersStat": "0.53892",
                                    "pMaxStat": "0.624",
                                    "RANK_BY_16Pers": "3",
                                    "RANK_BY_pMax": "2",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "2.5"
                                },
                                {
                                    "Dimension": "P",
                                    "16PersStat": "0.4012",
                                    "pMaxStat": "0.52",
                                    "RANK_BY_16Pers": "7",
                                    "RANK_BY_pMax": "3",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "5.0"
                                },
                                {
                                    "Dimension": "S",
                                    "16PersStat": "0.87545",
                                    "pMaxStat": "0.5152",
                                    "RANK_BY_16Pers": "1",
                                    "RANK_BY_pMax": "4",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "2.5"
                                },
                                {
                                    "Dimension": "N",
                                    "16PersStat": "0.12455",
                                    "pMaxStat": "0.4848",
                                    "RANK_BY_16Pers": "8",
                                    "RANK_BY_pMax": "5",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "6.5"
                                },
                                {
                                    "Dimension": "J",
                                    "16PersStat": "0.5988",
                                    "pMaxStat": "0.48",
                                    "RANK_BY_16Pers": "2",
                                    "RANK_BY_pMax": "6",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "4.0"
                                },
                                {
                                    "Dimension": "E",
                                    "16PersStat": "0.46108",
                                    "pMaxStat": "0.376",
                                    "RANK_BY_16Pers": "6",
                                    "RANK_BY_pMax": "7",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "6.5"
                                },
                                {
                                    "Dimension": "F",
                                    "16PersStat": "0.51617",
                                    "pMaxStat": "0.1728",
                                    "RANK_BY_16Pers": "4",
                                    "RANK_BY_pMax": "8",
                                    "ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)": "6.0"
                                }
                            ]
                        },
                        "text/html": "<table><tr><th>Dimension</th><th>16PersStat</th><th>pMaxStat</th><th>RANK_BY_16Pers</th><th>RANK_BY_pMax</th><th>ROUND(((RANK() OVER(ORDER BY 16PersStat DESC)) + (RANK() OVER(ORDER BY pMaxStat DESC)))/2,1)</th></tr><tr><td>T</td><td>0.48383</td><td>0.8272</td><td>5</td><td>1</td><td>3.0</td></tr><tr><td>I</td><td>0.53892</td><td>0.624</td><td>3</td><td>2</td><td>2.5</td></tr><tr><td>P</td><td>0.4012</td><td>0.52</td><td>7</td><td>3</td><td>5.0</td></tr><tr><td>S</td><td>0.87545</td><td>0.5152</td><td>1</td><td>4</td><td>2.5</td></tr><tr><td>N</td><td>0.12455</td><td>0.4848</td><td>8</td><td>5</td><td>6.5</td></tr><tr><td>J</td><td>0.5988</td><td>0.48</td><td>2</td><td>6</td><td>4.0</td></tr><tr><td>E</td><td>0.46108</td><td>0.376</td><td>6</td><td>7</td><td>6.5</td></tr><tr><td>F</td><td>0.51617</td><td>0.1728</td><td>4</td><td>8</td><td>6.0</td></tr></table>"
                    },
                    "metadata": {}
                }
            ],
            "execution_count": 42
        },
        {
            "cell_type": "markdown",
            "source": [
                "The S Dimension was the most prominent according to the 16 Personality Statistics, while the T Dimension was the most prominent according to the pMax Statistics.\n",
                "\n",
                "Combining the ranks together, the S and the I Dimension where the most prominent with the T Dimension coming at a close second. This shows that Sensing, Introversion and Thinking are popular personality type traits in the sample."
            ],
            "metadata": {
                "azdata_cell_guid": "615deaef-716c-4715-9718-494edd178f07"
            },
            "attachments": {}
        }
    ]
}