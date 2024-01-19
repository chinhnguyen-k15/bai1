# bai1
bai 1
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package bai1;

import java.net.InetAddress;
/**
 *
 * @author chinh
 */
public class Bai1 {

   public static void main(String[] args) {
        try {
           InetAddress inet=InetAddress.getByName("www.google.com");
           boolean isKN=inet.isReachable(5000);
           if(isKN)
           {
               System.out.println("Co Internet");
           }
           else
           {
               System.out.println("Khong co Inetnet");
           }
       } catch (Exception e) 
        { 
        }
    }
    
}
// Nguyen Dang Chinh CNTT 15-02
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Main.java to edit this template
 */
package bai2;

import java.net.InetAddress;
import java.net.UnknownHostException;

/**
 *
 * @author Chinh
 */
public class Bai2 {

   public static void main(String[] args) {
        try {
            InetAddress inet=InetAddress.getByName("www.google.com");
            System.out.println("Dia chi ip cua trang web google: " +
                    inet.getHostAddress());
        } catch (UnknownHostException e){
        }
        
    }
    
}
// Nguyen Dang Chinh CNTT 15-02
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package com.mycompany.javaapplication;

import java.net.InetAddress;
import java.net.NetworkInterface;
import java.net.SocketException;
import java.util.Enumeration;

/**
 *
 * @author chinh
 */

public class Bai3 {
    public static void main(String[] args) {
        try {
            Enumeration<NetworkInterface> netInterfaces = NetworkInterface.getNetworkInterfaces();

            while (netInterfaces.hasMoreElements()) {
                NetworkInterface networkInterface = netInterfaces.nextElement();
                Enumeration<InetAddress> inetAddresses = networkInterface.getInetAddresses();

                while (inetAddresses.hasMoreElements()) {
                    InetAddress address = inetAddresses.nextElement();
                    System.out.println("Interface: " + networkInterface.getName() + "; Dia chi IP: " + address.getHostAddress());
                }
            }
        } catch (SocketException e) {
        }
    }
}
