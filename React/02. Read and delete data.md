
```js
import { useEffect, useState } from "react";

import axios from "axios";

import toast, { Toaster } from 'react-hot-toast';

import Loading from "../loader/Loading";

  

const BlogRead = () => {

    const [blogData, setBlogData]=useState([]);

    const [refress, setRefress]=useState(0);

    const [loading, setLoading]=useState(true);

    //

    useEffect(()=>{

        blogReadApi();

    },[refress]);

  

    const blogReadApi = async ()=>{

        let res=await axios.get("https://crud.teamrabbil.com/api/v1/ReadProduct");

        let resData = res.data['data'];

        setBlogData(resData);

        setLoading(false);

    }

  

    ////

    const deleteApi =async(id)=>{

        setLoading(true);

        let res=await axios.get(`https://crud.teamrabbil.com/api/v1/DeleteProduct/${id}`);

        let deleteData = res.data['status'];

        if(deleteData=="success"){

            toast.success("Data delete success");

            blogReadApi();

        }else{

            toast.success("Data delete failed");

        }

    }

  
  
  

    return (

        <>

            {loading && <Loading/>}

            <div className="container">

                <div className="row">

                    <div className="com-12">

                        <h1>Blog List </h1>

                        <button onClick={()=>{setRefress(refress+1)}} className="btn btn-success">Refress</button>

                        <table className="table table-striped">

                        <thead>

                                <tr>

                                <th scope="col">Image</th>

                                <th scope="col">Id</th>

                                <th scope="col">Name</th>

                                <th scope="col">Code</th>

                                <th scope="col">price</th>

                                <th scope="col">qty</th>

                                <th scope="col">Total</th>

                                <th scope="col">Update time</th>

                                </tr>

                            </thead>

                            <tbody>

                                {

                                    blogData.length>0 &&

                                    blogData.map((item)=>{

                                        return(

                                            <tr>

                                                <td><img style={{width:'80px', height:'auto'}} src={item['Img']}/></td>

                                                <td>{item['_id']}</td>

                                                <td>{item['ProductName']}</td>

                                                <td>{item['ProductCode']}</td>

                                                <td>{item['UnitPrice']}"</td>

                                                <td>{item['Qty']}"</td>

                                                <td>{item['TotalPrice']}"</td>

                                                <td>{item['CreatedDate']}"</td>

                                                <td>

                                                    <button onClick={()=>{deleteApi(item['_id'])}} className="btn btn-danger w-100 m-1">Delete</button>

                                                    <button className="btn btn-primary w-100 m-1">Edit</button>

                                                </td>

                                            </tr>

                                        )

                                    })

                                }

                            </tbody>

                        </table>

                        <Toaster/>

                    </div>

                </div>

            </div>      

        </>

    );

};

  

export default BlogRead;
```