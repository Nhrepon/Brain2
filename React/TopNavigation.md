
```React
import React from "react";

import { Link } from "react-router-dom";

  

const TopNavigation = () => {

  return (

    <div className="container-fluid">

      <div className="container">

        <div className="row">

          <nav className="navbar navbar-expand-md navbar-light bg-transparent d-flex justify-content-between">

            <Link className="navbar-brand fw-bold" to="/">

              BEGUNI

            </Link>

  

            <button

              className="navbar-toggler"

              type="button"

              data-bs-toggle="collapse"

              data-bs-target="#navbarSupportedContent"

              aria-controls="navbarSupportedContent"

              aria-expanded="false"

              aria-label="Toggle navigation"

            >

              <span className="navbar-toggler-icon"></span>

            </button>

  

            <div className="collapse navbar-collapse gap-3 justify-content-end" id="navbarSupportedContent" >

              <ul className="navbar-nav mr-auto gap-3">

                <li className="nav-item">

                  <Link className="nav-link" to="/">

                    Home

                  </Link>

                </li>

                <li className="nav-item">

                  <Link className="nav-link" to="/blog">

                    Blog

                  </Link>

                </li>

                <li className="nav-item dropdown">

                  <a

                    className="nav-link dropdown-toggle"

                    href="#"

                    id="navbarDropdown"

                    role="button"

                    data-bs-toggle="dropdown"

                    aria-haspopup="true"

                    aria-expanded="false"

                  >

                    Group

                  </a>

                  <div

                    className="dropdown-menu"

                    aria-labelledby="navbarDropdown"

                  >

                    <Link className="dropdown-item" to="/blog">

                      Action

                    </Link>

                    <Link className="dropdown-item" to="/blog">

                      Another action

                    </Link>

                    <div className="dropdown-divider"></div>

                    <Link className="dropdown-item" to="/blog">

                      Something else here

                    </Link>

                  </div>

                </li>

                <li className="nav-item">

                  <Link className="nav-link " to="/about">About</Link>

                </li>

                <li className="nav-item">

                  <Link className="nav-link " to="/contact">Contact</Link>

                </li>

              </ul>

  
  

              <div className="d-md-flex gap-2">

              <div className="input-group">

                <input

                  className="form-control"

                  type="search"

                  placeholder="Search"

                  aria-label="Search"

                />

                <Link

                  to="/"

                  className="btn btn-outline-dark"

                  type="submit">

                  <svg

                    xmlns="http://www.w3.org/2000/svg"

                    fill="none"

                    viewBox="0 0 24 24"

                    stroke="currentColor"

                    style={{ width: 24, height: 24 }}>

                    <path

                      strokeLinecap="round"

                      strokeLinejoin="round"

                      strokeWidth={2}

                      d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"

                    />

                  </svg>

                </Link>

              </div>

              <Link

                to="/cart"

                type="button"

                className="btn ms-2 btn-light position-relative">

                <i className="bi text-dark bi-bag"></i>

                <span className="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-success">

                  4

                  <span className="visually-hidden">unread message</span>

                </span>

              </Link>

              <Link

                to="/wish"

                type="button"

                className="btn ms-2 btn-light d-flex position-relative">

                <i className="bi text-dark bi-heart"></i>

                <span className="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-success">

                  4

                  <span className="visually-hidden">unread message</span>

                </span>

              </Link>

  

              <Link

                  type="button"

                  className="btn ms-3 btn-success d-flex"

                  to="/login">

                  Login

                </Link>

            </div>

  
  
  
  
  

              <Link type="button" className="btn btn-outline-success px-3"  to="/login">Login</Link>

  
  
  

  

              </div>

  
  
  
  

          </nav>

        </div>

      </div>

    </div>

  );

};

  

export default TopNavigation;
```